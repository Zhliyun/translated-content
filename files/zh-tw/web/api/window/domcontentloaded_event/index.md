---
title: DOMContentLoaded
slug: Web/API/Window/DOMContentLoaded_event
translation_of: Web/API/Window/DOMContentLoaded_event
original_slug: Web/Events/DOMContentLoaded
---
<p><code>DOMContentLoaded事件是當document被完整的讀取跟解析後就會被觸發</code>,不會等待 stylesheets, 圖片和subframes完成讀取  (<code><a href="/en-US/docs/Mozilla_event_reference/load">load</a>事件可以用來作為判斷頁面已經完整讀取的方法</code>).</p>

<div class="note">
<p><strong>Note:</strong> <a href="http://molily.de/weblog/domcontentloaded">Stylesheet loads block script execution</a>, 如果 <code>&lt;script&gt;</code> 被放在 <code>&lt;link rel="stylesheet" ...&gt;後面的話</code>, 須等到前面的stylesheet載入並完成解析，此時 <code>DOMContentLoaded才會被觸發。</code></p>
</div>

<h2 id="Speeding_up">Speeding up</h2>

<p>If you want DOM to get parsed as fast as possible after the user had requested the page, some things you could do is turn your <a href="/en-US/docs/Web/API/XMLHttpRequest/Synchronous_and_Asynchronous_Requests">JavaScript asynchronous</a> and to <a href="https://developers.google.com/speed/docs/insights/OptimizeCSSDelivery">optimize loading of stylesheets</a> which if used as usual, slow down page load due to being loaded in parallel, "stealing" traffic from the main html document.</p>

<h2 id="General_info">General info</h2>

<dl>
 <dt>Specification</dt>
 <dd><a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/the-end.html#the-end">HTML5</a></dd>
 <dt>Interface</dt>
 <dd>Event</dd>
 <dt>Bubbles</dt>
 <dd>Yes</dd>
 <dt>Cancelable</dt>
 <dd>Yes (although specified as a simple event that isn't cancelable)</dd>
 <dt>Target</dt>
 <dd>Document</dd>
 <dt>Default Action</dt>
 <dd>None.</dd>
</dl>

<h2 id="屬性">屬性</h2>

<table>
 <thead>
  <tr>
   <th scope="col">Property</th>
   <th scope="col">Type</th>
   <th scope="col">Description</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>target</code> {{readonlyInline}}</td>
   <td>{{domxref("EventTarget")}}</td>
   <td>The event target (the topmost target in the DOM tree).</td>
  </tr>
  <tr>
   <td><code>type</code> {{readonlyInline}}</td>
   <td>{{domxref("DOMString")}}</td>
   <td>The type of event.</td>
  </tr>
  <tr>
   <td><code>bubbles</code> {{readonlyInline}}</td>
   <td>{{jsxref("Boolean")}}</td>
   <td>Whether the event normally bubbles or not.</td>
  </tr>
  <tr>
   <td><code>cancelable</code> {{readonlyInline}}</td>
   <td>{{jsxref("Boolean")}}</td>
   <td>Whether the event is cancellable or not.</td>
  </tr>
 </tbody>
</table>

<h2 id="規範">規範</h2>

{{Specifications}}

<h2 id="瀏覽器相容性">瀏覽器相容性</h2>

{{Compat("api.Window.DOMContentLoaded_event")}}

<h2 id="Related_Events">Related Events</h2>

<ul>
 <li>{{event("DOMContentLoaded")}}</li>
 <li>{{event("readystatechange")}}</li>
 <li>{{event("load")}}</li>
 <li>{{event("beforeunload")}}</li>
 <li>{{event("unload")}}</li>
</ul>