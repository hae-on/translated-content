---
title: Border-image 生成器
slug: Web/CSS/CSS_Backgrounds_and_Borders/Border-image_generator
tags:
  - CSS
  - Tools
translation_of: Web/CSS/CSS_Background_and_Borders/Border-image_generator
original_slug: Web/CSS/CSS_Background_and_Borders/Border-image_generator
---
<p>这个工具用于生成 CSS3 {{cssxref("border-image")}} 的值。</p>

<div class="hidden">
<h2 id="Border_Image_Generator">Border Image Generator</h2>

<h3 id="HTML_Content">HTML Content</h3>

<pre class="brush: html">    &lt;div id="container"&gt;

        &lt;div id="gallery"&gt;
            &lt;div id="image-gallery"&gt;
                &lt;img class="image" src="https://mdn.mozillademos.org/files/6007/border-image-1.png" data-stateID="border1"/&gt;
                &lt;img class="image" src="https://mdn.mozillademos.org/files/6009/border-image-2.png" data-stateID="border2"/&gt;
                &lt;img class="image" src="https://mdn.mozillademos.org/files/6011/border-image-3.png" data-stateID="border3"/&gt;
                &lt;img class="image" src="https://mdn.mozillademos.org/files/6013/border-image-4.png" data-stateID="border4"/&gt;
                &lt;img class="image" src="https://mdn.mozillademos.org/files/6015/border-image-5.png" data-stateID="border5"/&gt;
                &lt;img class="image" src="https://mdn.mozillademos.org/files/6017/border-image-6.svg" data-stateID="border6"/&gt;
            &lt;/div&gt;
        &lt;/div&gt;

        &lt;div id="load-actions" class="group section"&gt;
            &lt;div id="toggle-gallery" data-action="hide"&gt; &lt;/div&gt;
            &lt;div id="load-image" class="button"&gt; Upload image &lt;/div&gt;
            &lt;input id="remote-url" type="text" placeholder="Load an image from URL"/&gt;
            &lt;div id="load-remote" class="button"&gt; &lt;/div&gt;
        &lt;/div&gt;

        &lt;div id="general-controls" class="group section"&gt;
            &lt;div class="name"&gt; Control Box &lt;/div&gt;
            &lt;div class="separator"&gt;&lt;/div&gt;
            &lt;div class="property"&gt;
                &lt;div class="name"&gt;scale&lt;/div&gt;
                &lt;div class="ui-input-slider" data-topic="scale"
                    data-unit="%" data-max="300" data-sensivity="10"&gt;
                &lt;/div&gt;
            &lt;/div&gt;
            &lt;div class="separator"&gt;&lt;/div&gt;
            &lt;div class="property"&gt;
                &lt;div class="name"&gt;draggable&lt;/div&gt;
                &lt;div class="ui-checkbox" data-topic='drag-subject'&gt;&lt;/div&gt;
            &lt;/div&gt;
            &lt;div class="property right"&gt;
                &lt;div class="name"&gt;section height&lt;/div&gt;
                &lt;div class="ui-input-slider" data-topic="preview-area-height"
                    data-min="400" data-max="1000"&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/div&gt;

        &lt;div id="preview_section" class="group section"&gt;
            &lt;div id="subject"&gt;
                &lt;div class="guideline" data-axis="Y" data-topic="slice-top"&gt;&lt;/div&gt;
                &lt;div class="guideline" data-axis="X" data-topic="slice-right"&gt;&lt;/div&gt;
                &lt;div class="guideline" data-axis="Y" data-topic="slice-bottom"&gt;&lt;/div&gt;
                &lt;div class="guideline" data-axis="X" data-topic="slice-left"&gt;&lt;/div&gt;
            &lt;/div&gt;
            &lt;div id="preview"&gt; &lt;/div&gt;
        &lt;/div&gt;

        &lt;!-- controls --&gt;
        &lt;div id="controls" class="group section"&gt;

            &lt;!-- border-image-slice --&gt;
            &lt;div id="border-slice-control" class="category"&gt;
                &lt;div class="title"&gt; border-image-slice &lt;/div&gt;
                &lt;div class="property"&gt;
                    &lt;div class="name"&gt;fill&lt;/div&gt;
                    &lt;div class="ui-checkbox" data-topic='slice-fill'&gt;&lt;/div&gt;
                &lt;/div&gt;
            &lt;/div&gt;

            &lt;!-- border-image-width --&gt;
            &lt;div id="border-width-control" class="category"&gt;
                &lt;div class="title"&gt; border-image-width &lt;/div&gt;
            &lt;/div&gt;

            &lt;!-- border-image-outset --&gt;
            &lt;div id="border-outset-control" class="category"&gt;
                &lt;div class="title"&gt; border-image-outset &lt;/div&gt;
            &lt;/div&gt;

            &lt;!-- other-settings --&gt;
            &lt;div id="aditional-properties" class="category"&gt;
                &lt;div class="title"&gt; aditional-properties &lt;/div&gt;
                &lt;div class="property"&gt;
                    &lt;div class="name"&gt; repeat-x &lt;/div&gt;
                    &lt;div class="ui-dropdown border-repeat" data-topic="image-repeat-X" data-selected="2"&gt;
                        &lt;div data-value="0"&gt;repeat&lt;/div&gt;
                        &lt;div data-value="0"&gt;stretch&lt;/div&gt;
                        &lt;div data-value="0"&gt;round&lt;/div&gt;
                    &lt;/div&gt;
                &lt;/div&gt;
                &lt;div class="property"&gt;
                    &lt;div class="name"&gt; repeat-y &lt;/div&gt;
                    &lt;div class="ui-dropdown border-repeat" data-topic="image-repeat-Y" data-selected="2"&gt;
                        &lt;div data-value="1"&gt;repeat&lt;/div&gt;
                        &lt;div data-value="1"&gt;stretch&lt;/div&gt;
                        &lt;div data-value="1"&gt;round&lt;/div&gt;
                    &lt;/div&gt;
                &lt;/div&gt;
                &lt;div class="property"&gt;
                    &lt;div class="ui-input-slider" data-topic="font-size" data-info="em size"
                        data-unit="px" data-value="12" data-sensivity="3"&gt;
                    &lt;/div&gt;
                &lt;/div&gt;

                &lt;div class="property"&gt;
                    &lt;div class="ui-input-slider" data-topic="preview-width" data-info="width"
                         data-unit=" px" data-min="10" data-max="10000" data-sensivity="3"&gt;&lt;/div&gt;
                &lt;/div&gt;
                &lt;div class="property"&gt;
                    &lt;div class="ui-input-slider" data-topic="preview-height" data-info="height"
                        data-unit=" px" data-min="10" data-max="10000" data-sensivity="3"&gt;
                    &lt;/div&gt;
                &lt;/div&gt;
            &lt;/div&gt;


            &lt;div id="output" class="category"&gt;
                &lt;div class="title"&gt; CSS Code &lt;/div&gt;
                &lt;div class="css-property"&gt;
                    &lt;span class="name"&gt; border-image-slice: &lt;/span&gt;
                    &lt;span id="out-border-slice" class="value"&gt; &lt;/span&gt;
                &lt;/div&gt;
                &lt;div class="css-property"&gt;
                    &lt;span class="name"&gt; border-image-width: &lt;/span&gt;
                    &lt;span id="out-border-width" class="value"&gt; &lt;/span&gt;
                &lt;/div&gt;
                &lt;div class="css-property"&gt;
                    &lt;span class="name"&gt; border-image-outset: &lt;/span&gt;
                    &lt;span id="out-border-outset" class="value"&gt; &lt;/span&gt;
                &lt;/div&gt;
                &lt;div class="css-property"&gt;
                    &lt;span class="name"&gt; border-image-repeat: &lt;/span&gt;
                    &lt;span id="out-border-repeat" class="value"&gt; &lt;/span&gt;
                &lt;/div&gt;
                &lt;div class="css-property"&gt;
                    &lt;span class="name"&gt; border-image-source: &lt;/span&gt;
                    &lt;span id="out-border-source" class="value"&gt;  &lt;/span&gt;
                &lt;/div&gt;
            &lt;/div&gt;

        &lt;/div&gt;
    &lt;/div&gt;</pre>

<h3 id="CSS_Content">CSS Content</h3>

<pre class="brush: css">/*  GRID OF TWELVE
 * ========================================================================== */

.span_12 {
	width: 100%;
}

.span_11 {
	width: 91.46%;
}

.span_10 {
	width: 83%;
}

.span_9 {
	width: 74.54%;
}

.span_8 {
	width: 66.08%;
}

.span_7 {
	width: 57.62%;
}

.span_6 {
	width: 49.16%;
}

.span_5 {
	width: 40.7%;
}

.span_4 {
	width: 32.24%;
}

.span_3 {
	width: 23.78%;
}

.span_2 {
	width: 15.32%;
}

.span_1 {
	width: 6.86%;
}


/*  SECTIONS
 * ========================================================================== */

.section {
	clear: both;
	padding: 0px;
	margin: 0px;
}

/*  GROUPING
 * ========================================================================== */


.group:before, .group:after {
    content: "";
    display: table;
}

.group:after {
    clear:both;
}

.group {
    zoom: 1; /* For IE 6/7 (trigger hasLayout) */
}

/*  GRID COLUMN SETUP
 * ========================================================================== */

.col {
	display: block;
	float:left;
	margin: 1% 0 1% 1.6%;
}

.col:first-child {
	margin-left: 0;
} /* all browsers except IE6 and lower */



/*
 * UI Component
 */

.ui-input-slider {
	height: 20px;
	font-family: "Segoe UI", Arial, Helvetica, sans-serif;
	-moz-user-select: none;
	user-select: none;
}

.ui-input-slider * {
	float: left;
	height: 100%;
	line-height: 100%;
}

/* Input Slider */

.ui-input-slider &gt; input {
	margin: 0;
	padding: 0;
	width: 50px;
	text-align: center;

	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;
}

.ui-input-slider-info {
	width: 90px;
	padding: 0px 10px 0px 0px;
	text-align: right;
	text-transform: lowercase;
}

.ui-input-slider-left, .ui-input-slider-right {
	width: 16px;
	cursor: pointer;
	background: url("https://mdn.mozillademos.org/files/5679/arrows.png") center left no-repeat;
}

.ui-input-slider-right {
	background: url("https://mdn.mozillademos.org/files/5679/arrows.png") center right no-repeat;
}

.ui-input-slider-name {
	width: 90px;
	padding: 0 10px 0 0;
	text-align: right;
	text-transform: lowercase;
}

.ui-input-slider-btn-set {
	width: 25px;
	background-color: #2C9FC9;
	border-radius: 5px;
	color: #FFF;
	font-weight: bold;
	line-height: 14px;
	text-align: center;
}

.ui-input-slider-btn-set:hover {
	background-color: #379B4A;
	cursor: pointer;
}

/*************************************************************************************/
/*************************************************************************************/

/*
 * UI DropDown
 */

/* Dropdown */

.ui-dropdown {
	height: 2em;
	width: 120px;
	font-family: "Segoe UI", Arial, Helvetica, sans-serif;
	font-size: 12px;

	background-image: url("https://mdn.mozillademos.org/files/6037/drop_arrow_icon.png");
	background-position: right center;
	background-repeat: no-repeat;
	background-color: #359740;

	position: relative;

	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;

	-moz-user-select: none;
	-webkit-user-select: none;
	-ms-user-select: none;
	user-select: none;
}

.ui-dropdown:hover {
	cursor: pointer;
	background-color: #208B20;
}

/* Dropdown Select Button */

.ui-dropdown-select {
	height: inherit;
	padding: 0 0.75em;
	color: #FFF;
	line-height: 2em;
}

/* Dropdown List */

.ui-dropdown-list {
	width: 100%;
	height: 150px;
	max-height: 150px;
	margin: 0;
	padding: 0 0.3em;

	border: 3px solid #3490D2;
	border-color: #208B20;
	background: #666;
	background-color: #EEF1F5;
	color: #000;

	position: absolute;
	top: 2em;
	left: 0;
	z-index: 100;

	overflow: hidden;
	transition: all 0.3s;

	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;
}

.ui-dropdown-list:hover {
	overflow: auto;
}

.ui-dropdown-list[data-hidden='true'] {
	height: 0 !important;
	opacity: 0;
	visibility: hidden;
}

.ui-dropdown[data-position='left'] .ui-dropdown-list {
	left: -100%;
	top: 0;
}

.ui-dropdown[data-position='right'] .ui-dropdown-list {
	left: 100%;
	top: 0;
}

.ui-dropdown-list &gt; div {
	width: 100%;
	height: 1.6em;
	margin: 0.3em 0;
	padding: 0.3em;
	line-height: 1em;

	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;
}

.ui-dropdown-list &gt; div:hover {
	background: #3490D2;
	color:#FFF;
	border-radius: 2px;
	cursor: pointer;
}


/*************************************************************************************/
/*************************************************************************************/

/*
 * UI Button
 */

/* Checkbox */

.ui-checkbox {
	text-align: center;
	font-size: 16px;
	font-family: "Segoe UI", Arial, Helvetica, sans-serif;
	line-height: 1.5em;
	color: #FFF;

	-moz-user-select: none;
	-webkit-user-select: none;
	-ms-user-select: none;
	user-select: none;
}

.ui-checkbox &gt; input {
 	display: none;
}

.ui-checkbox &gt; label {
	font-size: 12px;
	padding: 0.333em 1.666em 0.5em;
	height: 1em;
	line-height: 1em;

	background-color: #888;
	background-image: url("https://mdn.mozillademos.org/files/5683/disabled.png");
	background-position: center center;
	background-repeat: no-repeat;

	color: #FFF;
	border-radius: 2px;
	font-weight: bold;
	float: left;
}

.ui-checkbox .text {
	padding-left: 34px;
	background-position: center left 10px;
}

.ui-checkbox .left {
	padding-right: 34px;
	padding-left: 1.666em;
	background-position: center right 10px;
}

.ui-checkbox &gt; label:hover {
	cursor: pointer;
}

.ui-checkbox &gt; input:checked + label {
	background-image: url("https://mdn.mozillademos.org/files/5681/checked.png");
	background-color: #379B4A;
}

/*************************************************************************************/
/*************************************************************************************/

/*
 * BORDER IMAGE GENERATOR TOOL
 */

body {
	width: 100%;
	margin: 0 auto;
	padding: 0 0 20px 0;

	font-family: "Segoe UI", Arial, Helvetica, sans-serif;

	/*background: url("https://mdn.mozillademos.org/files/6025/grain.png");*/
	border: 1px solid #EEE;

	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;

	-moz-user-select: none;
	-webkit-user-select: none;
	-ms-user-select: none;
	user-select: none;
}

body[data-move='X'] {
	cursor: w-resize !important;
}

body[data-move='Y'] {
	cursor: s-resize !important;
}

#container {
	width: 100%;

	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;
}

[data-draggable='true']:hover {
	cursor: move;
}

[data-draggable='true']:hover &gt; * {
	cursor: default;
}



/******************************************************************************/
/******************************************************************************/

/*
 * Border Image Picker
 */

#gallery {
	box-shadow: 0 0 3px 0 #BABABA;
}

#image-gallery {
	width: 600px;
	height: 100px;
	margin: 0 auto;
	transition: margin 0.4s;
}

#image-gallery .image {
	height: 80px;
	float: left;
	margin: 10px;
	opacity: 0.5;
	background-color: #FFF;
	box-shadow: 0px 0px 3px 1px #BABABA;
}

#image-gallery .image[selected="true"] {
	box-shadow: 0px 0px 3px 1px #3BBA52;
	opacity: 1;
}

#image-gallery .image:hover {
	cursor: pointer;
	box-shadow: 0px 0px 3px 1px #30ACE5;
	opacity: 1;
}

#image-gallery[data-collapsed='true'] {
	margin-top: -100px;
}

/* Load Menu */

#load-actions {
	margin: 10px 0;
}

#toggle-gallery {
	width: 30px;
	height: 25px;
	margin: 10px;
	color: #FFF;

	background-image: url('https://mdn.mozillademos.org/files/6005/arrow-up-white.png');
	background-repeat: no-repeat;
	background-position: top 4px center;
	background-color: #888888 !important;

	border-radius: 2px;
	float: left;
}

#toggle-gallery:hover {
	cursor: pointer;
}

#toggle-gallery[data-action='show'] {
	background-image: url('https://mdn.mozillademos.org/files/6001/arrow-down-white.png');
	background-color: #888888 !important;
}

#toggle-gallery[data-action='hide'] {
	background-image: url('https://mdn.mozillademos.org/files/6005/arrow-up-white.png');
}

.button {
	width: 100px;
	height: 25px;
	margin: 10px;
	color: #FFF;
	text-align: center;
	font-size: 12px;
	line-height: 25px;
	background-color: #379B4A;
	border-radius: 2px;
	float: left;
}

.button:hover {
	cursor: pointer;
	background-color: #3380C4;
}

#load-image {
	float: left;
}

#load-remote {
	width: 30px;
	background-image: url('https://mdn.mozillademos.org/files/6003/arrow-right-white.png');
	background-repeat: no-repeat;
	background-position: center center;
}

#remote-url {
	width: 200px;
	height: 23px;
	margin: 10px;
	padding: 0 5px;
	border: 1px solid #379B4A;
	border-radius: 2px;
	float: left;

	transition: width 0.5s;
}

#remote-url:focus {
	box-shadow: 0px 0px 3px -1px #379B4A; /*#68ACE8; */
	border-color: rgba(55, 155, 74, 0.5);
	width: 450px;
}

/*
 * Visible Area
 */

#preview_section {
	position: relative;
	min-height: 400px;
}

/* Image Control */

#subject {
	width: 300px;
	height: 300px;
	background-repeat: no-repeat;
	background-size: 100%;
	background-color: #FFF;
	border: 1px solid #CCC;

	position: absolute;
	z-index: 10;
	top: 15%;
	left: 10%;

	box-shadow: 0 0 3px 0 #BABABA;
	transition-property: width, height;
	transition-duration: 0.1s;
}

#subject .guideline {
	background-color: rgba(255, 255, 255, 0.7);
	border: 1px solid rgba(0, 0, 0, 0.3);
	position: absolute;
}

#subject .guideline:hover {
	background-color: #F00;
}

#subject .guideline[data-active] {
	background-color: #F00;
	z-index: 10;
}

#subject .guideline[data-axis='X'] {
	width: 1px;
	height: 100%;
	top: -1px;
}

#subject .guideline[data-axis='Y'] {
	width: 100%;
	height: 1px;
	left: -1px;
}

#subject .guideline[data-axis='X']:hover {
	cursor: w-resize;
}

#subject .guideline[data-axis='Y']:hover {
	cursor: s-resize;
}


#subject .relative {
	position: relative;
	font-size: 12px;
}

#subject .tooltip, #subject .tooltip2 {
	width: 40px;
	height: 20px;
	line-height: 20px;
	font-size: 12px;
	text-align: center;

	position: absolute;
	opacity: 0.5;
	transition: opacity 0.25s;
}

#subject .tooltip {
	background: #EEE;
	border-radius: 2px;
	border: 1px solid #CCC;
}

#subject .tooltip2{
	color: #555;
}

#subject [data-active] &gt; * {
	opacity: 1;
}

#subject .tooltip[data-info='top'] {
	top: -10px;
	right: -50px;
}

#subject .tooltip[data-info='right'] {
	bottom: -30px;
	right: -20px;
}

#subject .tooltip[data-info='bottom'] {
	top: -10px;
	left: -50px;
}

#subject .tooltip[data-info='left'] {
	top: -30px;
	right: -20px;
}

#subject .tooltip2[data-info='top'] {
	top: -10px;
	left: -50px;
}

#subject .tooltip2[data-info='right'] {
	top: -30px;
	right: -20px;
}

#subject .tooltip2[data-info='bottom'] {
	top: -10px;
	right: -50px;
}

#subject .tooltip2[data-info='left'] {
	bottom: -30px;
	right: -20px;
}

/* Preview */

#preview {
	width: 30%;
	height: 50%;
	background-color: #FFF;
	text-align: center;
	overflow: hidden;
	position: absolute;
	z-index: 10;

	left: 60%;
	top: 15%;

	border-radius: 2px;
	border-image-width: 20px;
	border-image-repeat: round;
	box-shadow: 0 0 3px 0 #BABABA;
}

#preview .resize-handle {
	width: 10px;
	height: 10px;
	background: url("https://mdn.mozillademos.org/files/6027/resize.png") center center no-repeat;
	position: absolute;
	bottom: 0;
	right: 0;
}

#preview .resize-handle:hover {
	cursor: nw-resize;
}


/*
 * General controls MENU
 */

#general-controls {
	padding: 10px 30px;
	background-color: #FFF;
	opacity: 0.95;
	color: #888;
	/*border-radius: 2px;*/
	box-shadow: 0 0 3px 0 #BABABA;
}

#general-controls .property {
	width: 130px;
	float: left;
}

#general-controls .name {
	height: 20px;
	margin: 0 10px 0 0;
	line-height: 100%;
	text-align: right;
	float: left;
}

#general-controls .right {
	width: 200px;
	float: right;
}

#general-controls .ui-checkbox label {
	height: 10px;
}

#general-controls .separator {
	height: 40px;
	width: 1px;
	margin: -10px 15px;
	background-color: #EEE;
	float: left;
}

/*
 * Controls
 */

#controls {
	color: #444;
	margin: 10px 0 0 0;
}

#controls .category {
	height: 190px;
	min-width: 260px;
	margin: 10px;
	padding: 10px;
	border: 1px solid #CCC;
	border-radius: 3px;
	float: left;

	box-shadow: 0 0 3px 0 #BABABA;
	transition: all 0.25s;

	-moz-box-sizing: border-box;
	-webkit-box-sizing: border-box;
	box-sizing: border-box;
}

@media (min-width: 880px) {
	#controls .category {
		width: 30%;
		margin-left: 1.66%;
		margin-right: 1.66%;
	}
}

@media (max-width: 879px) {
	#controls .category {
		width: 37%;
		margin-left: 6.5%;
		margin-right: 6.5%;
	}
}

#controls .category .title {
	width: 100%;
	height: 30px;
	margin: 0 0 10px 0;
	line-height: 25px;

	text-align: center;
	color: #AAA;
}

#controls .category:hover .title {
	color: #777;
}

#controls .category &gt; .group {
	border: 1px solid #CCC;
	border-radius: 2px;
}


/* property */

#controls .property {
	width: 250px;
	height: 20px;
	margin: 5px auto;
}

#controls .property .ui-input-slider {
	margin: 0;
	float: left;
}

#controls .property .ui-input-slider-info {
	width: 60px;
}

#controls .property .ui-input-slider-left {
	transition: opacity 0.15s;
    opacity: 0;
}

#controls .property .ui-input-slider-right {
	transition: opacity 0.15s;
    opacity: 0;
}

#controls .property .name {
	width: 60px;
	height: 20px;
	padding: 0px 10px 0px 0px;
	text-align: right;
	line-height: 100%;
	float: left;
}

#controls .property .config {
	width: 20px;
	height: 20px;
	float: left;
	background: url("https://mdn.mozillademos.org/files/6021/config.png") center center no-repeat;
	opacity: 0.5;
}

#controls .property .config:hover {
	cursor: pointer;
	opacity: 1;
}

#controls .ui-input-slider:hover .ui-input-slider-right {
    opacity: 1;
}

#controls .ui-input-slider:hover .ui-input-slider-left {
    opacity: 1;
}

#controls .property .ui-dropdown {
	margin: 0 10px;
	float: left;
}


#controls .property .ui-checkbox {
	margin: 0 0 0 16px;
	float: left;
}

#controls .property .ui-checkbox label {
	height: 0.85em;
	width: 10px;
}

/* dropdowns */
#controls .ui-dropdown {
	width: 50px;
	height: 1.7em;
	border-radius: 2px;
}

#controls .ui-dropdown-select {
	line-height: 1.6em;
}

#controls .ui-dropdown-list {
	top: 20px;
}

#controls .ui-dropdown-list {
	border-width: 1px;
	text-align: center;
}

#controls .ui-dropdown-list:hover {
	overflow: hidden;
}

#controls .border-repeat {
	margin: 0 0 0 16px !important;
	width: 80px;
}

#controls .border-repeat .ui-dropdown-list {
	height: 6.2em;
	border-width: 1px;
	text-align: center;
}

/* border-image-slice */


#border-slice-control .ui-dropdown-list {
	height: 4.3em;
}

/* border-image-width */

#border-width-control .ui-dropdown-list {
	height: 6.2em;
}

/* border-image-outset */

#border-outset-control .ui-dropdown-list {
	height: 4.3em;
}

#aditional-properties .property {
	width: 200px;
}

#aditional-properties .ui-input-slider &gt; input {
	width: 80px !important;
}

/* unit settings panel */

#unit-settings {
	padding: 10px;
	position: absolute;

	background: #FFF;

	font-size: 12px;
	border-radius: 3px;
	border: 1px solid #CCC;
	text-align: center;
	color: #555;

	position: absolute;
	z-index: 1000;

	box-shadow: 0 0 3px 0 #BABABA;
	transition: all 0.25s;
}

#unit-settings .title {
	width: 100%;
	margin: -5px auto 0;

	color: #666;
	font-size: 14px;
	font-weight: bold;
	line-height: 25px;
	border-bottom: 1px solid #E5E5E5;
}

#unit-settings .ui-input-slider {
	margin: 10px 0 0 0;
}

#unit-settings .ui-input-slider-info {
	width: 50px;
	line-height: 1.5em;
}

#unit-settings input {
	font-size: 12px;
	width: 40px !important;
}

#unit-settings .close {
	width: 16px;
	height: 16px;
	background: url('https://mdn.mozillademos.org/files/6019/close.png') no-repeat center center;
	background-size: 75%;

	position: absolute;
	top: 4px;
	right: 4px;
	opacity: 0.5;
}

#unit-settings .close:hover {
	cursor: pointer;
	opacity: 1;
}

#unit-settings[data-active='true'] {
	opacity: 1;
}

#unit-settings[data-active='false'] {
	opacity: 0;
	top: -100px !important;
}

/*
 * CSS Output Code
 */

#output {
	padding: 10px;
	border: 2px dashed #888 !important;
	box-shadow: none !important;
	border-radius: 3px;
	overflow: hidden;

	-moz-user-select: text;
	-webkit-user-select: text;
	-ms-user-select: text;
	user-select: text;
}


@media (min-width: 880px) {
	#output {
		width: 63.33% !important;
	}
}

@media (max-width: 879px) {
	#output {
		width: 87% !important;
	}
}


#output .title {
	width: 100%;
	height: 30px;
	margin: 0 0 10px 0;
	line-height: 25px;

	text-align: center;
	color: #AAA;
}

#output .css-property {
	width: 100%;
	margin: 0;
	color: #555;
	font-size: 14px;
	line-height: 18px;
	float: left;
}

#output .css-property .name {
	width: 30%;
	font-weight: bold;
	text-align: right;
	float: left;
}

#output .css-property .value {
	width: 65%;
	padding: 0 2.5%;
	word-break: break-all;
	float: left;
}

</pre>

<h3 id="JavaScript_Content">JavaScript Content</h3>

<pre class="brush: js">'use strict';

/**
 * UI-SlidersManager
 */

var InputSliderManager = (function InputSliderManager() {

	var subscribers = {};
	var sliders = [];

	var InputComponent = function InputComponent(obj) {
		var input = document.createElement('input');
		input.setAttribute('type', 'text');
		input.style.width = 50 + obj.precision * 10 + 'px';

		input.addEventListener('click', function(e) {
			this.select();
		});

		input.addEventListener('change', function(e) {
			var value = parseFloat(e.target.value);

			if (isNaN(value) === true)
				setValue(obj.topic, obj.value);
			else
				setValue(obj.topic, value);
		});

		return input;
	};

	var SliderComponent = function SliderComponent(obj, sign) {
		var slider = document.createElement('div');
		var startX = null;
		var start_value = 0;

		slider.addEventListener("click", function(e) {
			document.removeEventListener("mousemove", sliderMotion);
			setValue(obj.topic, obj.value + obj.step * sign);
		});

		slider.addEventListener("mousedown", function(e) {
			startX = e.clientX;
			start_value = obj.value;
			document.body.style.cursor = "e-resize";

			document.addEventListener("mouseup", slideEnd);
			document.addEventListener("mousemove", sliderMotion);
		});

		var slideEnd = function slideEnd(e) {
			document.removeEventListener("mousemove", sliderMotion);
			document.body.style.cursor = "auto";
			slider.style.cursor = "pointer";
		};

		var sliderMotion = function sliderMotion(e) {
			slider.style.cursor = "e-resize";
			var delta = (e.clientX - startX) / obj.sensivity | 0;
			var value = delta * obj.step + start_value;
			setValue(obj.topic, value);
		};

		return slider;
	};

	var InputSlider = function(node) {
		var min		= parseFloat(node.getAttribute('data-min'));
		var max		= parseFloat(node.getAttribute('data-max'));
		var step	= parseFloat(node.getAttribute('data-step'));
		var value	= parseFloat(node.getAttribute('data-value'));
		var topic	= node.getAttribute('data-topic');
		var unit	= node.getAttribute('data-unit');
		var name 	= node.getAttribute('data-info');
		var sensivity = node.getAttribute('data-sensivity') | 0;
		var precision = node.getAttribute('data-precision') | 0;

		this.min = isNaN(min) ? 0 : min;
		this.max = isNaN(max) ? 100 : max;
		this.precision = precision &gt;= 0 ? precision : 0;
		this.step = step &lt; 0 || isNaN(step) ? 1 : step.toFixed(precision);
		this.topic = topic;
		this.node = node;
		this.unit = unit === null ? '' : unit;
		this.sensivity = sensivity &gt; 0 ? sensivity : 5;
		value = isNaN(value) ? this.min : value;

		var input = new InputComponent(this);
		var slider_left  = new SliderComponent(this, -1);
		var slider_right = new SliderComponent(this,  1);

		slider_left.className = 'ui-input-slider-left';
		slider_right.className = 'ui-input-slider-right';

		if (name) {
			var info = document.createElement('span');
			info.className = 'ui-input-slider-info';
			info.textContent = name;
			node.appendChild(info);
		}

		node.appendChild(slider_left);
		node.appendChild(input);
		node.appendChild(slider_right);

		this.input = input;
		sliders[topic] = this;
		setValue(topic, value);
	};

	InputSlider.prototype.setInputValue = function setInputValue() {
		this.input.value = this.value.toFixed(this.precision) + this.unit;
	};

	var setValue = function setValue(topic, value, send_notify) {
		var slider = sliders[topic];
		if (slider === undefined)
			return;

		value = parseFloat(value.toFixed(slider.precision));

		if (value &gt; slider.max) value = slider.max;
		if (value &lt; slider.min)	value = slider.min;

		slider.value = value;
		slider.node.setAttribute('data-value', value);

		slider.setInputValue();

		if (send_notify === false)
			return;

		notify.call(slider);
	};

	var setMax = function setMax(topic, value) {
		var slider = sliders[topic];
		if (slider === undefined)
			return;

		slider.max = value;
		setValue(topic, slider.value);
	};

	var setMin = function setMin(topic, value) {
		var slider = sliders[topic];
		if (slider === undefined)
			return;

		slider.min = value;
		setValue(topic, slider.value);
	};

	var setUnit = function setUnit(topic, unit) {
		var slider = sliders[topic];
		if (slider === undefined)
			return;

		slider.unit = unit;
		setValue(topic, slider.value);
	};

	var setStep = function setStep(topic, value) {
		var slider = sliders[topic];
		if (slider === undefined)
			return;

		slider.step = parseFloat(value);
		setValue(topic, slider.value);
	};

	var setPrecision = function setPrecision(topic, value) {
		var slider = sliders[topic];
		if (slider === undefined)
			return;

		value = value | 0;
		slider.precision = value;

		var step = parseFloat(slider.step.toFixed(value));
		if (step === 0)
			slider.step = 1 / Math.pow(10, value);

		setValue(topic, slider.value);
	};

	var setSensivity = function setSensivity(topic, value) {
		var slider = sliders[topic];
		if (slider === undefined)
			return;

		value = value | 0;

		slider.sensivity = value &gt; 0 ? value : 5;
	};

	var getNode =  function getNode(topic) {
		return sliders[topic].node;
	};

	var getPrecision =  function getPrecision(topic) {
		return sliders[topic].precision;
	};

	var getStep =  function getStep(topic) {
		return sliders[topic].step;
	};

	var subscribe = function subscribe(topic, callback) {
		if (subscribers[topic] === undefined)
			subscribers[topic] = [];
		subscribers[topic].push(callback);
	};

	var unsubscribe = function unsubscribe(topic, callback) {
		subscribers[topic].indexOf(callback);
		subscribers[topic].splice(index, 1);
	};

	var notify = function notify() {
		if (subscribers[this.topic] === undefined)
			return;
		for (var i = 0; i &lt; subscribers[this.topic].length; i++)
			subscribers[this.topic][i](this.value);
	};

	var createSlider = function createSlider(topic, label) {
		var slider = document.createElement('div');
		slider.className = 'ui-input-slider';
		slider.setAttribute('data-topic', topic);

		if (label !== undefined)
			slider.setAttribute('data-info', label);

		new InputSlider(slider);
		return slider;
	};

	var init = function init() {
		var elem = document.querySelectorAll('.ui-input-slider');
		var size = elem.length;
		for (var i = 0; i &lt; size; i++)
			new InputSlider(elem[i]);
	};

	return {
		init : init,
		setMax : setMax,
		setMin : setMin,
		setUnit : setUnit,
		setStep : setStep,
		getNode : getNode,
		getStep : getStep,
		setValue : setValue,
		subscribe : subscribe,
		unsubscribe : unsubscribe,
		setPrecision : setPrecision,
		setSensivity : setSensivity,
		getPrecision : getPrecision,
		createSlider : createSlider,
	};

})();


/**
 * UI-DropDown Select
 */

var DropDownManager = (function DropdownManager() {

	var subscribers = {};
	var dropdowns = [];
	var active = null;

	var visbility = ["hidden", "visible"];


	var DropDown = function DropDown(node) {
		var topic = node.getAttribute('data-topic');
		var label = node.getAttribute('data-label');
		var selected = node.getAttribute('data-selected') | 0;

		var select = document.createElement('div');
		var list = document.createElement('div');
		var uval = 0;
		var option = null;
		var option_value = null;

		list.className = 'ui-dropdown-list';
		select.className = 'ui-dropdown-select';

		while (node.firstElementChild !== null) {
			option = node.firstElementChild;
			option_value = option.getAttribute('data-value');

			if (option_value === null)
				option.setAttribute('data-value', uval);

			list.appendChild(node.firstElementChild);
			uval++;
		}

		node.appendChild(select);
		node.appendChild(list);

		select.onclick = this.toggle.bind(this);
		list.onclick = this.updateValue.bind(this);
		document.addEventListener('click', clickOut);

		this.state = 0;
		this.time = 0;
		this.dropmenu = list;
		this.select = select;
		this.toggle(false);
		this.value = {};
		this.topic = topic;

		if (label)
			select.textContent = label;
		else
			this.setNodeValue(list.children[selected]);

		dropdowns[topic] = this;

	};

	DropDown.prototype.toggle = function toggle(state) {
		if (typeof(state) === 'boolean')
			this.state = state === false ? 0 : 1;
		else
			this.state = 1 ^ this.state;

		if (active !== this) {
			if (active)
				active.toggle(false);
			active = this;
		}

		if (this.state === 0)
			this.dropmenu.setAttribute('data-hidden', 'true');
		else
			this.dropmenu.removeAttribute('data-hidden');

	};

	var clickOut = function clickOut(e) {
		if (active.state === 0 ||
			e.target === active.dropmenu ||
			e.target === active.select)
			return;

		active.toggle(false);
	};

	DropDown.prototype.updateValue = function updateValue(e) {

		if (Date.now() - this.time &lt; 500)
			return;

		if (e.target.className !== "ui-dropdown-list") {
			this.setNodeValue(e.target);
			this.toggle(false);
		}

		this.time = Date.now();
	};

	DropDown.prototype.setNodeValue = function setNodeValue(node) {
		this.value['name'] = node.textContent;
		this.value['value'] = node.getAttribute('data-value');

		this.select.textContent = node.textContent;
		this.select.setAttribute('data-value', this.value['value']);

		notify.call(this);
	};

	var createDropDown = function createDropDown(topic, options) {

		var dropdown = document.createElement('div');
		dropdown.setAttribute('data-topic', topic);
		dropdown.className = 'ui-dropdown';

		for (var i in options) {
			var x = document.createElement('div');
			x.setAttribute('data-value', i);
			x.textContent = options[i];
			dropdown.appendChild(x);
		}

		new DropDown(dropdown);

		return dropdown;
	};

	var setValue = function setValue(topic, index) {
		if (dropdowns[topic] === undefined ||
			index &gt;= dropdowns[topic].dropmenu.children.length)
			return;

		dropdowns[topic].setNodeValue(dropdowns[topic].dropmenu.children[index]);
	};

	var subscribe = function subscribe(topic, callback) {
		if (subscribers[topic] === undefined)
			subscribers[topic] = [];
		subscribers[topic].push(callback);
	};

	var unsubscribe = function unsubscribe(topic, callback) {
		var index = subscribers[topic].indexOf(callback);
		subscribers[topic].splice(index, 1);
	};

	var notify = function notify() {
		if (subscribers[this.topic] === undefined)
			return;

		for (var i in subscribers[this.topic]) {
			subscribers[this.topic][i](this.value);
		}
	};

	var init = function init() {
		var elem, size;

		elem = document.querySelectorAll('.ui-dropdown');
		size = elem.length;
		for (var i = 0; i &lt; size; i++)
			new DropDown(elem[i]);

	};

	return {
		init : init,
		setValue : setValue,
		subscribe : subscribe,
		unsubscribe : unsubscribe,
		createDropDown : createDropDown
	};

})();


/**
 * UI-ButtonManager
 */

var ButtonManager = (function CheckBoxManager() {

	var subscribers = [];
	var buttons = [];

	var CheckBox = function CheckBox(node) {
		var topic = node.getAttribute('data-topic');
		var state = node.getAttribute('data-state');
		var name = node.getAttribute('data-label');
		var align = node.getAttribute('data-text-on');

		state = (state === "true");

		var checkbox = document.createElement("input");
		var label = document.createElement("label");

		var id = 'checkbox-' + topic;
		checkbox.id = id;
		checkbox.setAttribute('type', 'checkbox');
		checkbox.checked = state;

		label.setAttribute('for', id);
		if (name) {
			label.className = 'text';
			if (align)
				label.className += ' ' + align;
			label.textContent = name;
		}

		node.appendChild(checkbox);
		node.appendChild(label);

		this.node = node;
		this.topic = topic;
		this.checkbox = checkbox;

		checkbox.addEventListener('change', function(e) {
			notify.call(this);
		}.bind(this));

		buttons[topic] = this;
	};

	var getNode =  function getNode(topic) {
		return buttons[topic].node;
	};

	var setValue = function setValue(topic, value) {
		var obj = buttons[topic];
		if (obj === undefined)
			return;

		obj.checkbox.checked = value;
		notify.call(obj);
	};

	var subscribe = function subscribe(topic, callback) {
		if (subscribers[topic] === undefined)
			subscribers[topic] = [];

		subscribers[topic].push(callback);
	};

	var unsubscribe = function unsubscribe(topic, callback) {
		subscribers[topic].indexOf(callback);
		subscribers[topic].splice(index, 1);
	};

	var notify = function notify() {
		if (subscribers[this.topic] === undefined)
			return;
		for (var i = 0; i &lt; subscribers[this.topic].length; i++)
			subscribers[this.topic][i](this.checkbox.checked);
	};

	var init = function init() {
		var elem = document.querySelectorAll('.ui-checkbox');
		var size = elem.length;
		for (var i = 0; i &lt; size; i++)
			new CheckBox(elem[i]);
	};

	return {
		init : init,
		setValue : setValue,
		subscribe : subscribe,
		unsubscribe : unsubscribe
	};

})();

window.addEventListener("load", function() {
	BorderImage.init();
});

var BorderImage = (function BorderImage() {

	var getElemById = document.getElementById.bind(document);

	var subject;
	var preview;
	var guidelines = [];
	var positions = ['top', 'right', 'bottom', 'left'];

	var makeDraggable = function makeDraggable(elem) {

		var offsetTop;
		var offsetLeft;

		elem.setAttribute('data-draggable', 'true');

		var dragStart = function dragStart(e) {
			if (e.target.getAttribute('data-draggable') !== 'true' ||
				e.target !== elem || e.button !== 0)
				return;

			offsetLeft = e.clientX - elem.offsetLeft;
			offsetTop = e.clientY - elem.offsetTop;

			document.addEventListener('mousemove', mouseDrag);
			document.addEventListener('mouseup', dragEnd);
		};

		var dragEnd = function dragEnd(e) {
			if (e.button !== 0)
				return;

			document.removeEventListener('mousemove', mouseDrag);
			document.removeEventListener('mouseup', dragEnd);
		};

		var mouseDrag = function mouseDrag(e) {

			elem.style.left = e.clientX - offsetLeft + 'px';
			elem.style.top = e.clientY - offsetTop + 'px';
		};

		elem.addEventListener('mousedown', dragStart, false);
	};

	var PreviewControl = function PreviewControl() {

		var dragging = false;
		var valueX = null;
		var valueY = null;

		var dragStart = function dragStart(e) {
			if (e.button !== 0)
				return;

			valueX = e.clientX - preview.clientWidth;
			valueY = e.clientY - preview.clientHeight;
			dragging = true;

			document.addEventListener('mousemove', mouseDrag);
		};

		var dragEnd = function dragEnd(e) {
			if (e.button !== 0 || dragging === false)
				return;

			document.removeEventListener('mousemove', mouseDrag);
			dragging = false;
		};

		var mouseDrag = function mouseDrag(e) {
			InputSliderManager.setValue('preview-width', e.clientX - valueX);
			InputSliderManager.setValue('preview-height', e.clientY - valueY);
		};

		var init = function init() {

			makeDraggable(preview);
			makeDraggable(subject);

			var handle = document.createElement('div');
			handle.className = 'resize-handle';

			handle.addEventListener('mousedown', dragStart);
			document.addEventListener('mouseup', dragEnd);

			preview.appendChild(handle);

		};

		return {
			init: init
		};

	}();

	var ImageReader = (function ImageReader() {

		var fReader = new FileReader();
		var browse = document.createElement('input');

		var loadImage = function loadImage(e) {
			if (browse.files.length === 0)
				return;

			var file = browse.files[0];

			if (file.type.slice(0, 5) !== 'image')
				return;

			fReader.readAsDataURL(file);

			return false;
		};

		fReader.onload = function(e) {
			ImageControl.loadRemoteImage(e.target.result);
		};

		var load = function load() {
			browse.click();
		};

		browse.setAttribute('type', 'file');
		browse.style.display = 'none';
		browse.onchange = loadImage;

		return {
			load: load
		};

	})();

	var ImageControl = (function ImageControl() {

		var scale = 0.5;
		var imgSource = new Image();
		var imgState = null;
		var selected = null;


		var topics = ['slice', 'width', 'outset'];
		var properties = {};
		properties['border1'] = {
			fill			: false,

			slice_values	: [27, 27, 27, 27],
			width_values	: [20, 20, 20, 20],
			outset_values	: [0, 0, 0, 0],

			slice_units		: [0, 0, 0, 0],
			width_units		: [0, 0, 0, 0],
			outset_units	: [0, 0, 0, 0],

			repeat			: [1, 1],
			size			: [300, 200],
			preview_area	: 400
		};

		properties['border2'] = {
			fill			: false,

			slice_values	: [33, 33, 33, 33],
			width_values	: [1.5, 1.5, 1.5, 1.5],
			outset_values	: [0, 0, 0, 0],

			slice_units		: [1, 1, 1, 1],
			width_units		: [2, 2, 2, 2],
			outset_units	: [0, 0, 0, 0],

			repeat			: [2, 2],
			size			: [300, 200],
			preview_area	: 400
		};

		properties['border3'] = {
			fill			: true,

			slice_values	: [15, 15, 15, 15],
			width_values	: [10, 10, 10, 10],
			outset_values	: [0, 0, 0, 0],

			slice_units		: [0, 0, 0, 0],
			width_units		: [0, 0, 0, 0],
			outset_units	: [0, 0, 0, 0],

			repeat			: [2, 2],
			size			: [300, 200],
			preview_area	: 400
		};

		properties['border4'] = {
			fill			: false,

			slice_values	: [13, 13, 13, 13],
			width_values	: [13, 13, 13, 13],
			outset_values	: [13, 13, 13, 13],

			slice_units		: [0, 0, 0, 0],
			width_units		: [0, 0, 0, 0],
			outset_units	: [0, 0, 0, 0],

			repeat			: [0, 0],
			size			: [300, 200],
			preview_area	: 400
		};

		properties['border5'] = {
			fill			: false,

			slice_values	: [0, 12, 0, 12],
			width_values	: [0, 12, 0, 12],
			outset_values	: [0, 0, 0, 0],

			slice_units		: [0, 0, 0, 0],
			width_units		: [0, 0, 0, 0],
			outset_units	: [0, 0, 0, 0],

			repeat			: [0, 0],
			size			: [300, 200],
			preview_area	: 400,
		};

		properties['border6'] = {
			fill			: false,

			slice_values	: [42, 42, 42, 42],
			width_values	: [42, 42, 42, 42],
			outset_values	: [0, 0, 0, 0],

			slice_units		: [0, 0, 0, 0],
			width_units		: [0, 0, 0, 0],
			outset_units	: [0, 0, 0, 0],

			repeat			: [2, 2],
			size			: [350, 350],
			preview_area	: 500,
		};


		var loadLocalImage = function loadLocalImage(source) {
			var location = "images/" + source;
			imgSource.src = location;
		};

		var loadRemoteImage = function loadRemoteImage(source) {
			imgSource.src = source;
			if (selected)
				selected.removeAttribute('selected');
			Tool.setOutputCSS('source', 'url("' + source + '")');
		};

		var pickImage = function pickImage(e) {
			if (e.target.className === 'image') {
				selected = e.target;
				selected.setAttribute('selected', 'true');
				loadRemoteImage(e.target.src);
				imgState = e.target.getAttribute('data-stateID');
			}
		};

		var loadImageState = function loadImageState(stateID) {
			if (properties[stateID] === undefined)
				return;

			var prop = properties[stateID];
			var topic;
			var unit_array;
			var value_array;

			for (var i in topics) {
				for (var j=0; j&lt;4; j++) {
					topic = topics[i] + '-' + positions[j];
					unit_array = topics[i] + '_units';
					value_array = topics[i] + '_values';
					InputSliderManager.setValue(topic, prop[value_array][j]);
					DropDownManager.setValue(topic, prop[unit_array][j]);
				}
			}

			ButtonManager.setValue('slice-fill', prop['fill']);
			DropDownManager.setValue('image-repeat-X', prop['repeat'][0]);
			DropDownManager.setValue('image-repeat-Y', prop['repeat'][1]);
			InputSliderManager.setValue('preview-width', prop['size'][0]);
			InputSliderManager.setValue('preview-height', prop['size'][1]);
			InputSliderManager.setValue('preview-area-height', prop['preview_area']);
		};

		var update = function update() {
			scale =  Math.min(300, (30000 / this.width) | 0);
			setScale(scale);
			InputSliderManager.setValue('scale', scale, false);

			subject.style.backgroundImage = 'url("' + this.src + '")';
			preview.style.borderImageSource = 'url("' + this.src + '")';

			guidelines['slice-top'].setMax(this.height);
			guidelines['slice-right'].setMax(this.width);
			guidelines['slice-bottom'].setMax(this.height);
			guidelines['slice-left'].setMax(this.width);

			if (imgState)
				loadImageState(imgState);
		};

		var setScale = function setScale(value) {
			scale = value;
			var w = imgSource.width * scale / 100 | 0;
			var h = imgSource.height * scale / 100 | 0;
			subject.style.width = w + 'px';
			subject.style.height = h + 'px';

			for (var i = 0; i &lt; positions.length; i++)
				guidelines['slice-' + positions[i]].updateGuidelinePos();
		};

		var getScale = function getScale() {
			return scale/100;
		};

		var toggleGallery = function toggleGallery() {
			var gallery = getElemById('image-gallery');
			var button  = getElemById('toggle-gallery');
			var state = 1;
			button.addEventListener('click', function() {
				state = 1 ^ state;
				if (state === 0) {
					gallery.setAttribute('data-collapsed', 'true');
					button.setAttribute('data-action', 'show');
				}
				else {
					gallery.removeAttribute('data-collapsed');
					button.setAttribute('data-action', 'hide');
				}
			});
		};

		var init = function init() {
			var gallery = getElemById('image-gallery');
			var browse = getElemById('load-image');
			var remote = getElemById('remote-url');
			var load_remote = getElemById('load-remote');

			remote.addEventListener('change', function(){
				loadRemoteImage(this.value);
			});

			load_remote.addEventListener('click', function(){
				loadRemoteImage(remote.value);
			});

			browse.addEventListener('click', ImageReader.load);
			gallery.addEventListener('click', pickImage);
			imgSource.addEventListener('load', update);

			InputSliderManager.subscribe('scale', setScale);
			InputSliderManager.setValue('scale', scale);
			imgState = 'border1';
			loadRemoteImage('https://mdn.mozillademos.org/files/6007/border-image-1.png');
			toggleGallery();
		};

		return {
			init: init,
			getScale : getScale,
			loadRemoteImage: loadRemoteImage
		};

	})();

	var GuideLine = function GuideLine(node) {
		var topic = node.getAttribute('data-topic');
		var axis = node.getAttribute('data-axis');

		this.node = node;
		this.topic = topic;
		this.axis = axis;
		this.info = topic.split('-')[1];

		this.position = 0;
		this.value = 0;
		this.unit = 0;
		this.max = 0;
		this.pos = positions.indexOf(this.info);

		guidelines[topic] = this;

		var relative_container = document.createElement('div');
		var tooltip = document.createElement('div');
		var tooltip2 = document.createElement('div');

		tooltip.className = 'tooltip';
		tooltip.setAttribute('data-info', this.info);

		tooltip2.className = 'tooltip2';
		tooltip2.textContent = this.info;
		tooltip2.setAttribute('data-info', this.info);

		this.tooltip = tooltip;

		relative_container.appendChild(tooltip);
		relative_container.appendChild(tooltip2);
		node.appendChild(relative_container);

		var startX = 0;
		var startY = 0;
		var start = 0;

		var startDrag = function startDrag(e) {
			startX = e.clientX;
			startY = e.clientY;
			start = guidelines[topic].position;
			document.body.setAttribute('data-move', axis);
			relative_container.setAttribute('data-active', '');
			node.setAttribute('data-active', '');

			document.addEventListener('mousemove', updateGuideline);
			document.addEventListener('mouseup', endDrag);
		};

		var endDrag = function endDrag() {
			document.body.removeAttribute('data-move');
			relative_container.removeAttribute('data-active');
			node.removeAttribute('data-active');

			document.removeEventListener('mousemove', updateGuideline);
		};

		var updateGuideline = function updateGuideline(e) {
			var value;
			if (topic === 'slice-top')
				value = e.clientY - startY + start;

			if (topic === 'slice-right')
				value = startX - e.clientX + start;

			if (topic === 'slice-bottom')
				value = startY - e.clientY + start;

			if (topic === 'slice-left')
				value = e.clientX - startX + start;

			if (this.unit === 0)
				InputSliderManager.setValue(topic, value * 1 / ImageControl.getScale() | 0);
			else {
				InputSliderManager.setValue(topic, (value * 100 / (this.max * ImageControl.getScale())) | 0);
			}

		}.bind(this);

		node.addEventListener("mousedown", startDrag);

		InputSliderManager.subscribe(topic, this.setPosition.bind(this));
		InputSliderManager.setValue(topic, this.position);
	};


	GuideLine.prototype.updateGuidelinePos = function updateGuidelinePos() {
		if (this.unit === 0)
			this.position = this.value * ImageControl.getScale() | 0;
		else
			this.position = this.value * this.max * ImageControl.getScale() / 100 | 0;

		this.node.style[this.info] = this.position + 'px';
	};

	GuideLine.prototype.setPosition = function setPosition(value) {
		this.value = value;
		this.tooltip.textContent = value;
		this.updateGuidelinePos();
		Tool.setBorderSlice(this.pos, value);
	};

	GuideLine.prototype.setMax = function setMax(max) {
		this.max = max;
		this.updateLimit();
	};

	GuideLine.prototype.updateLimit = function updateLimit() {
		if (this.unit === 1)
			InputSliderManager.setMax(this.topic, 100);
		else
			InputSliderManager.setMax(this.topic, this.max);
	};

	GuideLine.prototype.setUnit = function setUnit(type) {
		if (type === '%')	this.unit = 1;
		if (type === '')	this.unit = 0;
		this.updateLimit();
	};

	/*
	 * Unit panel
	 */
	var UnitPanel = (function UnitPanel () {

		var panel;
		var title;
		var precision;
		var step;
		var unit_topic = null; // settings are made for this topic
		var step_option = [1, 0.1, 0.01];

		var updatePrecision = function updatePrecision(value) {
			InputSliderManager.setPrecision('unit-step', value);
			InputSliderManager.setStep('unit-step', step_option[value]);
			InputSliderManager.setMin('unit-step', step_option[value]);

			if (unit_topic)
				InputSliderManager.setPrecision(unit_topic, value);
		};

		var updateUnitSettings = function updateUnitSettings(value) {
			if (unit_topic)
				InputSliderManager.setStep(unit_topic, value);
		};

		var show = function show(e) {
			var topic = e.target.getAttribute('data-topic');
			var precision = InputSliderManager.getPrecision(topic);
			var step = InputSliderManager.getStep(topic);

			unit_topic = topic;
			title.textContent = topic;

			panel.setAttribute('data-active', 'true');
			panel.style.top = e.target.offsetTop - 40 + 'px';
			panel.style.left = e.target.offsetLeft + 30 + 'px';

			InputSliderManager.setValue('unit-precision', precision);
			InputSliderManager.setValue('unit-step', step);
		};

		var init = function init() {
			panel = document.createElement('div');
			title = document.createElement('div');
			var close = document.createElement('div');

			step = InputSliderManager.createSlider('unit-step', 'step');
			precision = InputSliderManager.createSlider('unit-precision', 'precision');

			InputSliderManager.setStep('unit-precision', 1);
			InputSliderManager.setMax('unit-precision', 2);
			InputSliderManager.setValue('unit-precision', 2);
			InputSliderManager.setSensivity('unit-precision', 20);

			InputSliderManager.setValue('unit-step', 1);
			InputSliderManager.setStep('unit-step', 0.01);
			InputSliderManager.setPrecision('unit-step', 2);

			InputSliderManager.subscribe('unit-precision', updatePrecision);
			InputSliderManager.subscribe('unit-step', updateUnitSettings);

			close.addEventListener('click', function () {
				panel.setAttribute('data-active', 'false');
			});

			title.textContent = 'Properties';
			title.className = 'title';
			close.className = 'close';
			panel.id = 'unit-settings';
			panel.setAttribute('data-active', 'false');
			panel.appendChild(title);
			panel.appendChild(precision);
			panel.appendChild(step);
			panel.appendChild(close);
			document.body.appendChild(panel);
		};

		return {
			init : init,
			show : show
		};

	})();

	/**
	 * Tool Manager
	 */
	var Tool = (function Tool() {
		var preview_area;
		var dropdown_unit_options = [
			{ '' : '--', '%' : '%'},
			{ 'px' : 'px', '%' : '%', 'em' : 'em'},
			{ 'px' : 'px', 'em' : 'em'},
		];

		var border_slice = [];
		var border_width = [];
		var border_outset = [];

		var border_slice_values = [];
		var border_width_values = [];
		var border_outset_values = [];

		var border_slice_units = ['', '', '', ''];
		var border_width_units = ['px', 'px', 'px', 'px'];
		var border_outset_units = ['px', 'px', 'px', 'px'];

		var border_fill = false;
		var border_repeat = ['round', 'round'];
		var CSS_code = {
			'source' : null,
			'slice' : null,
			'width' : null,
			'outset' : null,
			'repeat' : null
		};

		var setBorderSlice = function setBorderSlice(positionID, value) {
			border_slice[positionID] = value + border_slice_units[positionID];
			updateBorderSlice();
		};

		var updateBorderSlice = function updateBorderSlice() {
			var value = border_slice.join(' ');
			if (border_fill === true)
				value += ' fill';

			preview.style.borderImageSlice = value;
			setOutputCSS('slice', value);
		};

		var setBorderFill = function setBorderFill(value) {
			border_fill = value;
			var bimgslice = border_slice.join(' ');;
			if (value === true)
				bimgslice += ' fill';

			preview.style.borderImageSlice = bimgslice;
		};

		var updateBorderWidth = function updateBorderWidth() {
			var value = border_width.join(' ');
			preview.style.borderImageWidth = value;
			setOutputCSS('width', value);
		};

		var updateBorderOutset = function updateBorderOutset() {
			var value = border_outset.join(' ');
			preview.style.borderImageOutset = border_outset.join(' ');
			setOutputCSS('outset', value);
		};

		var setBorderRepeat = function setBorderRepeat(obj) {
			border_repeat[obj.value] = obj.name;
			var value = border_repeat.join(' ');
			preview.style.borderImageRepeat = value;
			setOutputCSS('repeat', value);
		};

		var setOutputCSS = function setOutputCSS(topic, value) {
			CSS_code[topic].textContent = value + ';';
		};

		var setPreviewFontSize = function setPreviewFontSize(value) {
			preview.style.fontSize = value + 'px';
		};

		var setPreviewWidth = function setPreviewWidth(value) {
			preview.style.width = value + 'px';
		};

		var setPreviewHeight = function setPreviewHeight(value) {
			preview.style.height = value + 'px';
		};

		var setPreviewAreaHeight = function setPreviewAreaHeight(value) {
			preview_area.style.height = value + 'px';
		};

		var updateDragOption = function updateDragOption(value) {
			if (value === true)
				subject.setAttribute('data-draggable', 'true');
			else
				subject.removeAttribute('data-draggable');
		};

		var createProperty = function createProperty(topic, labelID, optionsID) {

			var slider = InputSliderManager.createSlider(topic, positions[labelID]);
			var dropdown = DropDownManager.createDropDown(topic, dropdown_unit_options[optionsID]);

			InputSliderManager.setSensivity(topic, 3);
			InputSliderManager.setPrecision(topic, 1);

			var property = document.createElement('div');
			var config = document.createElement('div');

			property.className = 'property';
			config.className = 'config';
			config.setAttribute('data-topic', topic);
			config.addEventListener('click', UnitPanel.show);

			property.appendChild(slider);
			property.appendChild(dropdown);
			property.appendChild(config);

			return property;
		};

		var initBorderSliceControls = function initBorderSliceControls() {
			var container = getElemById('border-slice-control');

			var listenForChanges = function listenForChanges(topic, id) {
				InputSliderManager.subscribe(topic, function(value) {
					border_slice_values[id] = value;
					border_slice[id] = value + border_slice_units[id];
					updateBorderSlice();
				});

				DropDownManager.subscribe(topic, function(obj) {
					guidelines[topic].setUnit(obj.value);
					border_slice_units[id] = obj.value;
					border_slice[id] = border_slice_values[id] + obj.value;
					updateBorderSlice();
				});
			};

			for (var i = 0; i &lt; positions.length; i++) {
				var topic = 'slice-' + positions[i];
				var property = createProperty(topic, i, 0);
				listenForChanges(topic, i);

				container.appendChild(property);
			}

			container.appendChild(container.children[1]);

		};

		var initBorderWidthControls = function initBorderWidthControls() {
			var container = getElemById('border-width-control');

			var listenForChanges = function listenForChanges(topic, id) {
				InputSliderManager.subscribe(topic, function(value) {
					border_width_values[id] = value;
					border_width[id] = value + border_width_units[id];
					updateBorderWidth();
				});

				DropDownManager.subscribe(topic, function(obj) {
					if (obj.value === '%')
						InputSliderManager.setMax(topic, 100);
					else
						InputSliderManager.setMax(topic, 1000);

					border_width_units[id] = obj.value;
					border_width[id] = border_width_values[id] + obj.value;
					updateBorderWidth();
				});
			};

			for (var i = 0; i &lt; positions.length; i++) {
				var topic = 'width-' + positions[i];
				var property = createProperty(topic, i, 1);
				InputSliderManager.setMax(topic, 1000);
				listenForChanges(topic, i);

				container.appendChild(property);
			}
		};

		var initBorderOutsetControls = function initBorderOutsetControls() {

			var container = getElemById('border-outset-control');

			var listenForChanges = function listenForChanges(topic, id) {
				InputSliderManager.subscribe(topic, function(value) {
					border_outset_values[id] = value;
					border_outset[id] = value + border_outset_units[id];
					updateBorderOutset();
				});

				DropDownManager.subscribe(topic, function(obj) {
					border_outset_units[id] = obj.value;
					border_outset[id] = border_outset_values[id] + obj.value;
					updateBorderOutset();
				});
			};

			for (var i = 0; i &lt; positions.length; i++) {
				var topic = 'outset-' + positions[i];
				var property = createProperty(topic, i, 2);
				InputSliderManager.setMax(topic, 1000);
				listenForChanges(topic, i);

				container.appendChild(property);
			}
		};

		var init = function init() {

			var gallery =
			subject = getElemById('subject');
			preview = getElemById("preview");
			preview_area = getElemById("preview_section");


			CSS_code['source'] = getElemById("out-border-source");
			CSS_code['slice'] = getElemById("out-border-slice");
			CSS_code['width'] = getElemById("out-border-width");
			CSS_code['outset'] = getElemById("out-border-outset");
			CSS_code['repeat'] = getElemById("out-border-repeat");

			initBorderSliceControls();
			initBorderWidthControls();
			initBorderOutsetControls();

			var elem = document.querySelectorAll('.guideline');
			var size = elem.length;
			for (var i = 0; i &lt; size; i++)
				new GuideLine(elem[i]);

			PreviewControl.init();

			ButtonManager.subscribe('slice-fill',setBorderFill);
			ButtonManager.subscribe('drag-subject', updateDragOption);
			ButtonManager.setValue('drag-subject', false);

			DropDownManager.subscribe('image-repeat-X', setBorderRepeat);
			DropDownManager.subscribe('image-repeat-Y', setBorderRepeat);

			InputSliderManager.subscribe('preview-area-height', setPreviewAreaHeight);
			InputSliderManager.subscribe('preview-width', setPreviewWidth);
			InputSliderManager.subscribe('preview-height', setPreviewHeight);
			InputSliderManager.subscribe('font-size', setPreviewFontSize);
			InputSliderManager.setValue('preview-width', 300);
			InputSliderManager.setValue('preview-height', 200);
		};

		return {
			init: init,
			setOutputCSS: setOutputCSS,
			setBorderSlice: setBorderSlice
		};

	})();

	/**
	 * Init Tool
	 */
	var init = function init() {
		InputSliderManager.init();
		DropDownManager.init();
		ButtonManager.init();
		UnitPanel.init();
		Tool.init();
		ImageControl.init();
	};

	return {
		init : init
	};

})();

</pre>
</div>

<p>{{ EmbedLiveSample('Border_Image_Generator', '100%', '1270px') }}</p>

<p> </p>