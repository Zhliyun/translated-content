---
title: HTMLElement.click()
slug: Web/API/HTMLElement/click
translation_of: Web/API/HTMLElement/click
---
<div>
<div>{{ APIRef("HTML DOM") }}</div>
</div>

<p><code><strong>HTMLElement.click()</strong></code> 方法可以模擬滑鼠點擊一個元素。</p>

<p>當 <code>click()</code> 被使用在支援的元素（例如任一 {{HTMLElement("input")}} 元素），便會觸發該元素的點擊事件。事件會冒泡至 document tree（或 event chain）的上層元素，並觸發它們的點擊事件。其中的例外是：<code>click()</code> 方法不會讓 {{HTMLElement("a")}} 元素和接收到真實滑鼠點擊一樣進行頁面跳轉。</p>

<h2 id="語法">語法</h2>

<pre class="syntaxbox"><em>elt</em>.click()</pre>

<h2 id="規範">規範</h2>

{{Specifications}}

<h2 id="瀏覽器相容性">瀏覽器相容性</h2>

{{Compat("api.HTMLElement.click")}}