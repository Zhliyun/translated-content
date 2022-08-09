---
title: Event.isTrusted
slug: Web/API/Event/isTrusted
translation_of: Web/API/Event/isTrusted
---
<p>{{APIRef("DOM")}}</p>

<p>{{domxref("Event")}} 介面的 <code>isTrusted</code> 唯讀屬性為一個布林值，若事件物件是由使用者操作而產生，則 <code>isTrusted</code> 值為 <code>true</code>。若事件物件是由程式碼所建立、修改，或是透過 {{domxref("EventTarget.dispatchEvent()")}} 來觸發，則 <code>isTrusted</code> 值為 <code>false</code>。</p>

<h2 id="Syntax">語法</h2>

<pre class="syntaxbox">var bool = event.isTrusted;
</pre>

<h2 id="範例">範例</h2>

<pre> if (e.isTrusted) {
     /* The event is trusted. */
 } else {
     /* The event is not trusted. */
 }
</pre>

<h2 id="規範">規範</h2>

{{Specifications}}

<h2 id="瀏覽器相容性">瀏覽器相容性</h2>

{{Compat("api.Event.isTrusted")}}