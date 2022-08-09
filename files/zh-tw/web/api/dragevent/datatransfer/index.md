---
title: DragEvent.dataTransfer
slug: Web/API/DragEvent/dataTransfer
translation_of: Web/API/DragEvent/dataTransfer
---
<div>{{APIRef("HTML Drag and Drop API")}}</div>

<p><code><strong>DataEvent.dataTransfer</strong></code> 屬性保留了拖曳操作中的資料（指向一個 {{domxref("DataTransfer")}} 物件）。</p>

<p>此屬性為 {{readonlyInline}}。</p>

<h2 id="語法">語法</h2>

<pre class="syntaxbox">var <var>data</var> = <var>dragEvent</var>.dataTransfer;
</pre>

<h3 id="回傳值">回傳值</h3>

<dl>
 <dt><code>data</code></dt>
 <dd>一個保存 {{domxref("DragEvent")}} 當中資料的 {{domxref("DataTransfer")}} 物件。</dd>
</dl>

<h2 id="範例">範例</h2>

<p>This example illustrates accessing the drag and drop data within the {{event("dragend")}} event handler.</p>

<pre class="brush: js">function process_data(d) {
   // Process the data ...
}

dragTarget.addEventListener("dragend", function(ev) {
   // Call the drag and drop data processor
   if (ev.dataTransfer != null) process_data(ev.dataTransfer);
 }, false);
</pre>

<h2 id="規範">規範</h2>

{{Specifications}}

<h2 id="瀏覽器相容性">瀏覽器相容性</h2>

{{Compat("api.DragEvent.dataTransfer")}}