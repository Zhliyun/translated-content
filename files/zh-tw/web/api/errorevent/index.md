---
title: ErrorEvent
slug: Web/API/ErrorEvent
translation_of: Web/API/ErrorEvent
---
<p>{{APIRef("HTML DOM")}}</p>

<p><strong><code>ErrorEvent</code></strong> 介面是用來提供程式碼或是檔案的錯誤訊息的事件。</p>

<h2 id="Properties">Properties</h2>

<p><em>此介面繼承了其父 {{domxref("Event")}} 的 properties 。</em></p>

<dl>
 <dt>{{domxref("ErrorEvent.message")}} {{readonlyInline}}</dt>
 <dd>一 {{domxref("DOMString")}} 提供具可讀性的關於問題的錯誤訊息。</dd>
 <dt>{{domxref("ErrorEvent.filename")}} {{readonlyInline}}</dt>
 <dd>一 {{domxref("DOMString")}} ，為發生錯誤的程式碼檔案的檔名。</dd>
 <dt>{{domxref("ErrorEvent.lineno")}} {{readonlyInline}}</dt>
 <dd>一 <code>整數</code> ，為發生問題的程式的行數。</dd>
 <dt>{{domxref("ErrorEvent.colno")}} {{readonlyInline}}</dt>
 <dd>一 <code>整數</code> ，為發生問題的程式的欄數。</dd>
 <dt>{{domxref("ErrorEvent.error")}} {{readonlyInline}} {{experimental_inline}}</dt>
 <dd>一個參與該事件的 JavaScript <code>Object</code> 。</dd>
</dl>

<h2 id="Constructor">Constructor</h2>

<dl>
 <dt>{{domxref("ErrorEvent.ErrorEvent", "ErrorEvent()")}}</dt>
 <dd>建立一 <code>ErrorEvent</code> 事件，其包含提供的參數。</dd>
</dl>

<h2 id="Methods">Methods</h2>

<p><em>此介面繼承了其父 {{domxref("Event")}} 的 methods。</em></p>

<h2 id="Specifications">Specifications</h2>

{{Specifications}}

<h2 id="瀏覽器支援度比較">瀏覽器支援度比較</h2>

{{Compat("api.ErrorEvent")}}

<h2 id="延伸閱讀">延伸閱讀</h2>

<ul>
 <li><a href="/en-US/docs/Web/Guide/Performance/Using_web_workers">Using web workers</a>, most likely objects to raise such an event</li>
</ul>