---
title: WebSocket
slug: Web/API/WebSocket
tags:
  - WebSockets
translation_of: Web/API/WebSocket
original_slug: WebSockets/WebSockets_reference/WebSocket
---
<p>{{ SeeCompatTable() }}</p>

<p><code>WebSocket</code> 物件提供了建立、管理 <a href="/zh_tw/WebSockets">WebSocket</a> 伺服器連線的 API，它也有在連線中傳送、接收資料的能力。</p>

<h2 id="Method_overview">方法一覽</h2>

<table>
 <tbody>
  <tr>
   <td><code>void <a href="#close()">close</a>(in optional unsigned long code, in optional DOMString reason);</code></td>
  </tr>
  <tr>
   <td><code>void <a href="#send">send</a>(in DOMString data);</code></td>
  </tr>
 </tbody>
</table>

<h2 id="Attributes">屬性</h2>

<table>
 <tbody>
  <tr>
   <td class="header">屬性</td>
   <td class="header">形態</td>
   <td class="header">描述</td>
  </tr>
  <tr>
   <td><code>binaryType</code></td>
   <td>{{ DOMXref("DOMString") }}</td>
   <td>表示連線傳輸的二進制資料形態的字串，若使用 {{ domxref("Blob") }} 物件則為 "blob"，使用 <a href="/zh_tw/JavaScript_typed_arrays/ArrayBuffer"><code>ArrayBuffer</code></a> 物件則為 "arraybuffer"。</td>
  </tr>
  <tr>
   <td><code>bufferedAmount</code></td>
   <td><code><a href="/en/unsigned_long">unsigned long</a></code></td>
   <td>呼叫 <a href="#send"><code>send()</code></a> 隊列但尚未傳輸至網路上資料的位元數。連線關閉時此值不會重設為零。連續呼叫 <a href="#send"><code>send()</code></a> 會讓此值不斷上升。<strong>唯讀</strong></td>
  </tr>
  <tr>
   <td><code>extensions</code></td>
   <td>{{ DOMXref("DOMString") }}</td>
   <td>伺服器選擇的擴展。目前僅有空字串或表示資料經過壓縮的 "deflate-stream"。<strong>唯讀</strong></td>
  </tr>
  <tr>
   <td><code>onclose</code></td>
   <td>{{ domxref("EventListener") }}</td>
   <td>當 WebSocket 連線的 <code>readyState</code> 切換至 <code>CLOSED</code> 時呼叫的事件監聽器。監聽器接收命名為 "close" 的 <a href="/zh_tw/WebSockets/WebSockets_reference/CloseEvent"><code>CloseEvent</code></a>。</td>
  </tr>
  <tr>
   <td><code>onerror</code></td>
   <td>{{ domxref("EventListener") }}</td>
   <td>當錯誤發生時呼叫的事件監聽器。事件為命名 "error" 的簡單事件。</td>
  </tr>
  <tr>
   <td><code>onmessage</code></td>
   <td>{{ domxref("EventListener") }}</td>
   <td>當瀏覽器接收伺服器的訊息時呼叫的事件監聽器。監聽器接收命名為 "message" 的 <a href="/zh_tw/WebSockets/WebSockets_reference/MessageEvent"><code>MessageEvent</code></a>。</td>
  </tr>
  <tr>
   <td><code>onopen</code></td>
   <td>{{ domxref("EventListener") }}</td>
   <td>當 WebSocket 連線的 <code>readyState</code> 切換至 <code>OPEN</code> 時呼叫的事件監聽器，表示連線已準備傳送、接收資料。事件為命名 "open" 的簡單事件。</td>
  </tr>
  <tr>
   <td><code>protocol</code></td>
   <td>{{ DOMXref("DOMString") }}</td>
   <td>伺服器選擇的子協定，這是建立 WebSocket 物件時 <code>protocols</code> 參數裡的其中一個字串。</td>
  </tr>
  <tr>
   <td><code>readyState</code></td>
   <td><code><a href="/en/unsigned_short">unsigned short</a></code></td>
   <td>連線的目前狀態，是就緒狀態常數的其中一個。<strong>唯讀</strong></td>
  </tr>
  <tr>
   <td><code>url</code></td>
   <td>{{ DOMXref("DOMString") }}</td>
   <td>建構方法解析出來的 URL，總是絕對 URL。<strong>唯讀</strong></td>
  </tr>
 </tbody>
</table>

<h2 id="Constants">常數</h2>

<h3 id="就緒狀態常數">就緒狀態常數</h3>

<p><code>readyState</code> 屬性使用以下常數描述 WebSocket 的連線狀態。</p>

<table>
 <tbody>
  <tr>
   <td class="header">常數</td>
   <td class="header">值</td>
   <td class="header">描述</td>
  </tr>
  <tr>
   <td><code>CONNECTING</code></td>
   <td><code>0</code></td>
   <td>連線尚未打開。</td>
  </tr>
  <tr>
   <td><code>OPEN</code></td>
   <td><code>1</code></td>
   <td>連線已打開，可以進行通訊。</td>
  </tr>
  <tr>
   <td><code>CLOSING</code></td>
   <td><code>2</code></td>
   <td>連線正在進行關閉程序。</td>
  </tr>
  <tr>
   <td><code>CLOSED</code></td>
   <td><code>3</code></td>
   <td>連線已關閉／連線不能打開。</td>
  </tr>
 </tbody>
</table>

<h2 id="Methods">方法</h2>

<h3 id="close()">close()</h3>

<p>關閉 WebSocket 連線／連線嘗試，若連線已為 <code>CLOSED</code>，此方法沒有作用。</p>

<pre class="eval">void close(
  in optional unsigned short code,
  in optional DOMString reason
);
</pre>

<h4 id="Parameters">參數</h4>

<dl>
 <dt><code>code</code> {{ optional_inline() }}</dt>
 <dd>表示狀態代碼，狀態代碼用以解釋連線關閉的原因。若未指定參數，預設值為 1000（表示正常的「事務完結（transaction complete）」關閉）。請參考 <a href="/zh_tw/WebSockets/WebSockets_reference/CloseEvent"><code>CloseEvent</code></a> 頁面的<a href="/zh_tw/WebSockets/WebSockets_reference/CloseEvent#.e7.8b.80.e6.85.8b.e4.bb.a3.e7.a2.bc">狀態代碼列表</a>，有所有的合法值。</dd>
 <dt><code>reason</code> {{ optional_inline() }}</dt>
 <dd>解釋連線關閉原因的人類可讀字串，字串必不可大於 123 個 UTF-8 字符。</dd>
</dl>

<h4 id="可丟例外">可丟例外</h4>

<dl>
 <dt><code>INVALID_ACCESS_ERR</code></dt>
 <dd>指定不合法的 <code>code</code>。</dd>
 <dt><code>SYNTAX_ERR</code></dt>
 <dd><code>reason</code> 字串太長或是含有未配對的代理對。</dd>
</dl>

<h3 id="send()">send()</h3>

<p>透過 WebSocket 連線傳輸資料至伺服器。</p>

<pre class="eval">void send(
  in DOMString data
);

void send(
  in ArrayBuffer data
);

void send(
  in Blob data
);
</pre>

<h4 id="Parameters">參數</h4>

<dl>
 <dt><code>data</code></dt>
 <dd>要傳送至伺服器的字串。</dd>
</dl>

<h4 id="可丟例外_2">可丟例外</h4>

<dl>
 <dt><code>INVALID_STATE_ERR</code></dt>
 <dd>目前連線不為 <code>OPEN</code>。</dd>
 <dt><code>SYNTAX_ERR</code></dt>
 <dd>資料為帶有未配對代理對的字串。</dd>
</dl>

<h4 id="註釋">註釋</h4>

<div class="note">
<p>Gecko <code>send()</code> 方法的實作與 Gecko 6.0 的規範有差別。Gecko 回傳一個 <code>boolean</code> 以表示連線是否仍處於開啟狀態（且資料成功隊列／傳輸）。另外，此時此刻，Gecko 不支援 <code><a href="/zh_tw/JavaScript_typed_arrays/ArrayBuffer">ArrayBuffer</a></code> 或 {{ domxref("Blob") }} 作為資料形態。</p>
</div>

<h2 id="See_also">參見</h2>

<ul>
 <li><a href="/zh_tw/WebSockets/Writing_WebSocket_client_applications">製作 WebSocket 客戶端應用程式</a></li>
 <li><a href="http://dev.w3.org/html5/websockets/">HTML5: WebSockets</a></li>
</ul>

<h2 id="瀏覽器兼容">瀏覽器兼容</h2>

{{Compat("api.WebSocket")}}