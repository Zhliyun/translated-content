---
title: 203 Non-Authoritative Information
slug: Web/HTTP/Status/203
translation_of: Web/HTTP/Status/203
---
<div>{{HTTPSidebar}}</div>

<p>HTTP <strong><code>203 Non-Authoritative Information</code></strong> 狀態碼表明請求成功，但是與原始伺服器的 {{HTTPStatus("200")}} (<code>OK</code>) 回應相比，隨附的酬載已被具轉換功能的 {{Glossary("Proxy server", "代理伺服器")}} 所修改。</p>

<p><code>203</code> 回應相似於 {{HTTPHeader("Warning")}} 標頭的 <code><a href="/en-US/docs/Web/HTTP/Headers/Warning#Warning_codes">214</a> Transformation Applied</code>，但後者的額外的優點在於可以套用到任何狀態碼的回應中。</p>

<h2 id="狀態">狀態</h2>

<pre class="syntaxbox">203 Non-Authoritative Information</pre>

<h2 id="規範">規範</h2>

{{Specifications}}

<h2 id="參見">參見</h2>

<ul>
 <li>{{HTTPStatus("200")}}</li>
 <li>{{Glossary("Proxy server")}}</li>
 <li>{{HTTPHeader("Warning")}}</li>
</ul>