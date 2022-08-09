---
title: Blob.type
slug: Web/API/Blob/type
translation_of: Web/API/Blob/type
---
<div>{{APIRef("File API")}}</div>

<p><a href="/en-US/docs/Web/API/Blob"><code>Blob</code></a> 物件的 <strong><code>type</code></strong> 屬性提供檔案的 <a href="/zh-TW/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Complete_list_of_MIME_types">MIME 類別</a>。若無法辨明型別則回傳空字串。</p>

<h2 id="語法">語法</h2>

<pre class="syntaxbox">var mimetype = <var>instanceOfFile</var>.type</pre>

<h2 id="值">值</h2>

<p>一個字串。</p>

<h2 id="範例">範例</h2>

<pre class="brush:js">var i, fileInput, files, allowedFileTypes;

// fileInput 是個 HTMLInputElement: &lt;input type="file" multiple id="myfileinput"&gt;
fileInput = document.getElementById("myfileinput");

// files 是個 FileList 物件 （類似 NodeList）
files = fileInput.files;

// 這範例接受 *.png, *.jpeg 和 *.gif 圖片。
allowedFileTypes = ["image/png", "image/jpeg", "image/gif"];

for (i = 0; i &lt; files.length; i++) {
  // 測試 file.type 是否是允許的類別。
  if (allowedFileTypes.indexOf(<strong>files[i].type</strong>) &gt; -1) {
    // 若符合則執行這裡的程式碼。
  }
});
</pre>

<h2 id="規格">規格</h2>

{{Specifications}}

<h2 id="瀏覽器相容性">瀏覽器相容性</h2>

{{Compat("api.Blob.type")}}

<h2 id="參見">參見</h2>

<ul>
 <li>{{domxref("Blob")}}</li>
</ul>