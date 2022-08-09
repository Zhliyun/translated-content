---
title: MediaSource.duration
slug: Web/API/MediaSource/duration
translation_of: Web/API/MediaSource/duration
---
<div>{{APIRef("Media Source Extensions")}}{{SeeCompatTable}}</div>

<p>{{domxref("MediaSource")}} 介面的 <code><strong>duration</strong></code> 屬性用來取得以及設置正被表示的媒體時間長度。</p>

<h2 id="語法">語法</h2>

<pre class="brush: js">mediaSource.duration = 5.5; // 5.5 seconds

var myDuration = mediaSource.duration;</pre>

<h3 id="回傳值">回傳值</h3>

<p>單位為秒的 double 型別。</p>

<h3 id="錯誤">錯誤</h3>

<p>當設置此屬性一個新的值時以下錯誤可能發生。</p>

<table>
 <thead>
  <tr>
   <th scope="col">錯誤</th>
   <th scope="col">解釋</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><code>InvalidAccessError</code></td>
   <td>嘗試設置的時間長度是負值，或者 <code>NaN</code>。</td>
  </tr>
  <tr>
   <td><code>InvalidStateError</code></td>
   <td>{{domxref("MediaSource.readyState")}} 不是 <code>open</code>，或者 {{domxref("MediaSource.sourceBuffers")}} 中一個或多個以上的 {{domxref("SourceBuffer")}} 物件正在被更新（例如：他們的 {{domxref("SourceBuffer.updating")}} 屬性為 <code>true</code>。）</td>
  </tr>
 </tbody>
</table>

<h2 id="範例">範例</h2>

<p>以下的片段基於 Nick Desaulniers 所編纂的簡單範例（<a href="http://nickdesaulniers.github.io/netfix/demo/bufferAll.html">觀看實際演示</a>，或者<a href="https://github.com/nickdesaulniers/netfix/blob/gh-pages/demo/bufferAll.html">下載原始碼</a>以利更進一步研究。）</p>

<pre class="brush: js  language-js"><code class="language-js">function sourceOpen (_) {
  //console.log(this.readyState); // open
  var mediaSource = this;
  var sourceBuffer = mediaSource.addSourceBuffer(mimeCodec);
  fetchAB(assetURL, function (buf) {
    sourceBuffer.addEventListener('updateend', function (_) {
      mediaSource.endOfStream();
      mediaSource.duration = 120;
      video.play();
      //console.log(mediaSource.readyState); // ended
    });
    sourceBuffer.appendBuffer(buf);
  });
};

...</code></pre>

<h2 id="規格">規格</h2>

{{Specifications}}

<h2 id="相容性表格">相容性表格</h2>

{{Compat("api.MediaSource.duration")}}

<h2 id="相關資料">相關資料</h2>

<ul>
 <li>{{domxref("SourceBuffer")}}</li>
 <li>{{domxref("SourceBufferList")}}</li>
</ul>