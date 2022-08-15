---
title: CSS Scrollbars
slug: Web/CSS/CSS_Scrollbars
translation_of: Web/CSS/CSS_Scrollbars
---
<div>{{CSSRef}}{{SeeCompatTable}}</div>

<p><strong>CSS Scrollbars</strong>标准化了由 ie5 引入的废弃的滚动条颜色属性</p>

<h2 id="基础例子">基础例子</h2>

<p>在这个例子里 我们选择使用一个比较细的 滚动轨道为绿色，滚动块为紫色的滚动条</p>

<div id="Example">
<pre class="brush:css">.scroller {
  width: 300px;
  height: 100px;
  overflow-y: scroll;
  scrollbar-color: rebeccapurple green;
  scrollbar-width: thin;
}</pre>

<h3 id="HTML">HTML</h3>

<pre class="brush: html">&lt;div class="scroller"&gt;
Veggies es bonus vobis, proinde vos postulo essum magis kohlrabi
welsh onion daikon amaranth tatsoi tomatillo melon azuki bean garlic.
Gumbo beet greens corn soko endive gumbo gourd. Parsley shallot courgette
tatsoi pea sprouts fava bean collard greens dandelion okra wakame tomato.
Dandelion cucumber earthnut pea peanut soko zucchini.
&lt;/div&gt;</pre>

<h3 id="Result">Result</h3>

<p>{{EmbedLiveSample("Example")}}</p>
</div>

<h2 id="Reference">Reference</h2>

<h3 id="CSS_Properties">CSS Properties</h3>

<div class="index">
<ul>
 <li>{{CSSxRef("scrollbar-width")}}</li>
 <li>{{CSSxRef("scrollbar-color")}}</li>
</ul>
</div>

<h2 id="Specifications">Specifications</h2>

{{Specifications}}

<h2 id="Accessibility_concerns">Accessibility concerns</h2>

<p>When you customize scrollbars, consider they have enough contrast and that their hit area is large enough for people who use touch input.</p>

<ul>
 <li><a href="http://adrianroselli.com/2019/01/baseline-rules-for-scrollbar-usability.html">Baseline Rules for Scrollbar Usability | Adrian Roselli</a></li>
</ul>

<h2 id="Browser_compatibility">Browser compatibility</h2>

{{Compat}}