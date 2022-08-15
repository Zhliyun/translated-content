---
title: CSS 그레이디언트 사용하기
slug: Web/CSS/CSS_Images/Using_CSS_gradients
tags:
  - Advanced
  - CSS
  - CSS Images
  - Example
  - Gradients
  - Guide
  - Web
translation_of: Web/CSS/CSS_Images/Using_CSS_gradients
---
<div>{{CSSRef}}</div>

<p><strong>CSS 그레이디언트</strong>는 {{cssxref("&lt;image&gt;")}} 자료형의 특별한 종류인 {{cssxref("&lt;gradient&gt;")}}로 나타내며 두 개 이상의 색 간의 점진적 전환을 표현합니다. 그레이디언트에는 선형({{cssxref("linear-gradient")}} 함수), 방사형({{cssxref("radial-gradient")}} 함수), 각진 원형({{cssxref("conic-gradient")}} 함수) 세 종류가 있으며, 각각의 변형본으로 계속해서 반복하는 {{cssxref("repeating-linear-gradient")}}, {{cssxref("repeating-radial-gradient")}}, {{cssxref("repeating-conic-gradient")}} 함수도 있습니다.</p>

<p>그레이디언트는 배경처럼 <code>&lt;image&gt;</code>를 사용하는 곳에는 어디에나 적용할 수 있습니다. 그레이디언트는 동적으로 생성하므로, 비슷한 효과를 보기 위해 래스터 이미지를 사용하는 방식을 사용하지 않아도 됩니다. 또한 브라우저가 직접 생성하므로 확대했을 때 래스터 이미지보다 좋은 품질을 보이며 크기 조절도 즉시 가능합니다.</p>

<p>우선 선형 그레이디언트의 소개로 시작하여, 모든 유형의 그레이디언트에서 통용되는 기능을 선형으로 설명하고, 그 후에 방사형과 각진 원형, 마지막으로 반복 그레이디언트에 대해 알아보겠습니다.</p>

<h2 id="선형_그레이디언트_사용하기">선형 그레이디언트 사용하기</h2>

<p>선형 그레이디언트는 직선으로 진행하는 색상 무늬를 생성합니다.</p>

<div>
<h3 id="기본_선형_그레이디언트">기본 선형 그레이디언트</h3>

<p>가장 기본적인 그레이디언트 종류를 생성하기 위해서는 두 가지의 색만 지정하면 됩니다. 각각의 색을 "색상 정지점"이라고 부릅니다. 최소 두 가지가 필요하지만, 제한 없이 원하는 만큼 추가할 수 있습니다.</p>

<div class="hidden">
<pre class="brush: html notranslate" dir="rtl">&lt;div class="simple-linear"&gt;&lt;/div&gt;</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.simple-linear {
  background: linear-gradient(blue, pink);
}</pre>

<p>{{ EmbedLiveSample('기본_선형_그레이디언트', 120, 120) }}</p>
</div>

<div>
<h3 id="방향_전환">방향 전환</h3>

<p>기본적으로, 선형 그레이디언트는 위에서 아래로 진행합니다. 그러나 방향을 지정함으로써 그레이디언트를 회전할 수 있습니다.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="horizontal-gradient"&gt;&lt;/div&gt;</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.horizontal-gradient {
  background: linear-gradient(to right, blue, pink);
}
</pre>

<p>{{ EmbedLiveSample('방향_전환', 120, 120) }}</p>
</div>

<div>
<h3 id="대각선_그레이디언트">대각선 그레이디언트</h3>

<p>그레이디언트가 한쪽 모서리에서 다른 쪽 모서리를 잇는 대각선 방향으로 진행하도록 할 수도 있습니다.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="diagonal-gradient"&gt;&lt;/div&gt;</pre>

<pre class="brush: css notranslate">div {
  width: 200px;
  height: 100px;
}</pre>
</div>

<pre class="brush: css notranslate">.diagonal-gradient {
  background: linear-gradient(to bottom right, blue, pink);
}
</pre>

<p>{{ EmbedLiveSample('대각선_그레이디언트', 200, 100) }}</p>
</div>

<div>
<h3 id="각도_사용">각도 사용</h3>

<p>더 정밀하게 방향을 지정하고 싶다면 특정 각도를 지정할 수 있습니다.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="angled-gradient"&gt;&lt;/div&gt;</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.angled-gradient {
  background: linear-gradient(70deg, blue, pink);
}
</pre>

<p>{{ EmbedLiveSample('각도_사용', 120, 120) }}</p>

<p>각도를 사용할 때 <code>0deg</code> 는 아래쪽에서 위쪽으로 진행하는 선형 그레이디언트를, <code>90deg</code> 는 왼쪽에서 오른쪽으로, 등등 시계 방향으로 회전합니다. 음의 각도는 시계 반대 방향으로 회전합니다.</p>

<p><img alt="linear_redangles.png" class="default internal" src="/files/3811/linear_red_angles.png"></p>
</div>

<h2 id="색상_선언_효과_생성">색상 선언 &amp; 효과 생성</h2>

<p>All<span class="js-about-item-abstr"> CSS gradient types are a range of position-dependent colors. The colors produced by CSS gradients can vary continuously with position, producing smooth color transitions. It is also possible to create bands of solid colors, and hard transitions between two colors. The following are valid for all gradient functions:</span></p>

<div>
<h3 id="두_개보다_많은_색_사용하기">두 개보다 많은 색 사용하기</h3>

<p>You don't have to limit yourself to two colors—you may use as many as you like! By default, colors are evenly spaced along the gradient.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="auto-spaced-linear-gradient"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.auto-spaced-linear-gradient {
  background: linear-gradient(red, yellow, blue, orange);
}
</pre>

<p>{{ EmbedLiveSample('두_개보다_많은_색_사용하기', 120, 120) }}</p>
</div>

<div>
<h3 id="Positioning_color_stops">Positioning color stops</h3>

<p>You don't have to leave your color stops at their default positions. To fine-tune their locations, you can give each one zero, one, or two percentage or, for radial and linear gradients, absolute length values. If you specify the location as a percentage, <code>0%</code> represents the starting point, while <code>100%</code> represents the ending point; however, you can use values outside that range if necessary to get the effect you want. If you leave a location unspecified, the position of that particular color stop will be automatically calculated for you, with the first color stop being at <code>0%</code> and the last color stop being at <code>100%</code>, and any other color stops being half way between their adjacent color stops.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="multicolor-linear"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.multicolor-linear {
   background: linear-gradient(to left, lime 28px, red 77%, cyan);
}
</pre>

<p>{{ EmbedLiveSample('Positioning_color_stops', 120, 120) }}</p>
</div>

<div>
<h3 id="Creating_hard_lines">Creating hard lines</h3>

<p>To create a hard line between two colors, creating a stripe instead of a gradual transition, adjacent color stops can be set to the same location. In this example, the colors share a color stop at the <code>50%</code> mark, halfway through the gradient:</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="striped"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.striped {
   background: linear-gradient(to bottom left, cyan 50%, palegoldenrod 50%);
}</pre>

<p>{{ EmbedLiveSample('Creating_hard_lines', 120, 120) }}</p>
</div>

<div>
<h3 id="Gradient_hints">Gradient hints</h3>

<p>By default, the gradient transitions evenly from one color to the next. You can include a color-hint to move the midpoint of the transition value to a certain point along the gradient. In this example, we've moved the midpoint of the transition from the 50% mark to the 10% mark.</p>

<div class="hidden">
<pre class="brush: html notranslate" dir="rtl">&lt;div class="color-hint"&gt;&lt;/div&gt;
&lt;div class="simple-linear"&gt;&lt;/div&gt;</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px; float: left; margin-right: 10px;
}</pre>
</div>

<pre class="brush: css notranslate">.color-hint {
  background: linear-gradient(blue, 10%, pink);
}
.simple-linear {
  background: linear-gradient(blue, pink);
}</pre>

<p>{{ EmbedLiveSample('Gradient_hints', 120, 120) }}</p>
</div>

<div>
<h3 id="Creating_color_bands_stripes">Creating color bands &amp; stripes</h3>

<p>To include a solid, non-transitioning color area within a gradient, include two positions for the color stop. Color stops can have two positions, which is equivalent to two consecutive color stops with the same color at different positions. The color will reach full saturation at the first color stop, maintain that saturation through to the second color stop, and transition to the adjacent color stop's color through the adjacent color stop's first position.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="multiposition-stops"&gt;&lt;/div&gt;
&lt;div class="multiposition-stop2"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
  float: left; margin-right: 10px; box-sizing: border-box;
}</pre>
</div>

<pre class="brush: css notranslate">.multiposition-stops {
   background: linear-gradient(to left,
       lime 20%, red 30%, red 45%, cyan 55%, cyan 70%, yellow 80% );
   background: linear-gradient(to left,
       lime 20%, red 30% 45%, cyan 55% 70%, yellow 80% );
}
.multiposition-stop2 {
   background: linear-gradient(to left,
      lime 25%, red 25%, red 50%, cyan 50%, cyan 75%, yellow 75% );
   background: linear-gradient(to left,
      lime 25%, red 25% 50%, cyan 50% 75%, yellow 75% );
}
</pre>

<p>{{ EmbedLiveSample('Creating_color_bands_stripes', 120, 120) }}</p>

<p>In the first example above, the lime goes from the 0% mark, which is implied, to the 20% mark, transitions from lime to red over the next 10% of the width of the gradient, reach solid red at the 30% mark, and staying solid red up until 45% through the gradient, where it fades to cyan, being fully cyan for 15% of the gradient, and so on.</p>

<p>In the second example, the second color stop for each color is at the same location as the first color stop for the adjacent color, creating a striped effect.</p>

<p>In both examples, the gradient is written twice: the first is the CSS Images Level 3 method of repeating the color for each stop and the second example is the CSS Images Level 4 multiple color stop method of including two color-stop-lengths in a linear-color-stop declaration.</p>
</div>

<div>
<h3 id="Controlling_the_progression_of_a_gradient">Controlling the progression of a gradient</h3>

<p>By default, a gradient evenly progresses between the colors of two adjacent color stops, with the midpoint between those two color stops being the midpoint color value. You can control the interpolation, or progression, between two color stops by including a color hint location. In this example, the color reaches the midpoint between lime and cyan 20% of the way through the gradient rather than 50% of the way through. The second example does not contain the hint to hilight the difference the color hint can make:</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="colorhint-gradient"&gt;&lt;/div&gt; &lt;div class="regular-progression"&gt;&lt;/div&gt;

</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
  float: left; margin-right: 10px; box-sizing: border-box;
}</pre>
</div>

<pre class="brush: css notranslate">.colorhint-gradient {
  background: linear-gradient(to top, black, 20%, cyan);
}
.regular-progression {
  background: linear-gradient(to top, black, cyan);
}
</pre>

<p>{{ EmbedLiveSample('Controlling_the_progression_of_a_gradient', 120, 120) }}</p>
</div>

<h3 id="Overlaying_gradients">Overlaying gradients</h3>

<p>Gradients support transparency, so you can stack multiple backgrounds to achieve some pretty fancy effects. The backgrounds are stacked from top to bottom, with the first specified being on top.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="layered-image"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 300px;
  height: 150px;
}</pre>
</div>

<pre class="brush: css notranslate">.layered-image {
  background: linear-gradient(to right, transparent, mistyrose),
      url("https://mdn.mozillademos.org/files/15525/critters.png");
}
</pre>

<p>{{ EmbedLiveSample('Overlaying_gradients', 300, 150) }}</p>

<h3 id="Stacked_gradients">Stacked gradients</h3>

<p>You can even stack gradients with other gradients. As long as the top gradients aren't entirely opaque, the gradients below will still be visible.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="stacked-linear"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 200px;
  height: 200px;
}</pre>
</div>

<pre class="brush: css notranslate">.stacked-linear {
  background:
      linear-gradient(217deg, rgba(255,0,0,.8), rgba(255,0,0,0) 70.71%),
      linear-gradient(127deg, rgba(0,255,0,.8), rgba(0,255,0,0) 70.71%),
      linear-gradient(336deg, rgba(0,0,255,.8), rgba(0,0,255,0) 70.71%);
}
</pre>

<p>{{ EmbedLiveSample('Stacked_gradients', 200, 200) }}</p>

<h2 id="Using_radial_gradients">Using radial gradients</h2>

<p>Radial gradients are similar to linear gradients, except that they radiate out from a central point. You can dictate where that central point is. You can also make them circular or elliptical.</p>

<h3 id="A_basic_radial_gradient">A basic radial gradient</h3>

<p>As with linear gradients, all you need to create a radial gradient are two colors. By default, the center of the gradient is at the 50% 50% mark, and the gradient is elliptical matching the aspect ratio of it's box:</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="simple-radial"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 240px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.simple-radial {
  background: radial-gradient(red, blue);
}
</pre>

<p>{{ EmbedLiveSample('A_basic_radial_gradient', 120, 120) }}</p>

<h3 id="Positioning_radial_color_stops">Positioning radial color stops</h3>

<p>Again like linear gradients, you can position each radial color stop with a percentage or absolute length.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="radial-gradient"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.radial-gradient {
  background: radial-gradient(red 10px, yellow 30%, #1e90ff 50%);
}
</pre>

<p>{{ EmbedLiveSample('Positioning_radial_color_stops', 120, 120) }}</p>

<h3 id="Positioning_the_center_of_the_gradient">Positioning the center of the gradient</h3>

<p>You can position the center of the gradient with keyterms, percentage, or absolute lengths, length and percentage values repeating if only one is present, otherwise in the order of position from the left and position from the top.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="radial-gradient"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 240px;
}</pre>
</div>

<pre class="brush: css notranslate">.radial-gradient {
  background: radial-gradient(at 0% 30%, red 10px, yellow 30%, #1e90ff 50%);
}
</pre>

<p>{{ EmbedLiveSample('Positioning_the_center_of_the_gradient', 120, 120) }}</p>

<h3 id="Sizing_radial_gradients">Sizing radial gradients</h3>

<p>Unlike linear gradients, you can specify the size of radial gradients. Possible values include closest-corner, closest-side, farthest-corner, and farthest-side, with farthest-corner being the default.</p>

<h4 id="Example_closest-side_for_ellipses">Example: closest-side for ellipses</h4>

<p>This example uses the <code>closest-side</code> size value, which means the size is set by the distance from the starting point (the center) to the closest side of the enclosing box.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="radial-ellipse-side"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 240px;
  height: 100px;
}</pre>
</div>

<pre class="brush: css notranslate">.radial-ellipse-side {
  background: radial-gradient(ellipse closest-side,
      red, yellow 10%, #1e90ff 50%, beige);
}
</pre>

<p>{{ EmbedLiveSample('Example_closest-side_for_ellipses', 240, 100) }}</p>

<h4 id="Example_farthest-corner_for_ellipses">Example: farthest-corner for ellipses</h4>

<p>This example is similar to the previous one, except that its size is specified as <code>farthest-corner</code>, which sets the size of the gradient by the distance from the starting point to the farthest corner of the enclosing box from the starting point.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="radial-ellipse-far"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 240px;
  height: 100px;
}</pre>
</div>

<pre class="brush: css notranslate">.radial-ellipse-far {
  background: radial-gradient(ellipse farthest-corner at 90% 90%,
      red, yellow 10%, #1e90ff 50%, beige);
}
</pre>

<p>{{ EmbedLiveSample('Example_farthest-corner_for_ellipses', 240, 100) }}</p>

<h4 id="Example_closest-side_for_circles">Example: closest-side for circles</h4>

<p>This example uses <code>closest-side</code>, which makes the circle's size to be the distance between the starting point (the center) and the closest side. The circle's radius is the distance between the center of the gradient and the closest edge, which due to the positioning of the 25% from the top and 25% from the bottom, is closest to the bottom, since the height in this case is narrower than the width.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="radial-circle-close"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 240px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.radial-circle-close {
  background: radial-gradient(circle closest-side at 25% 75%,
      red, yellow 10%, #1e90ff 50%, beige);
}
</pre>

<p>{{ EmbedLiveSample('Example_closest-side_for_circles', 240, 120) }}</p>

<h3 id="Stacked_radial_gradients">Stacked radial gradients</h3>

<p>Just like linear gradients, you can also stack radial gradients. The first specified is on top, the last on the bottom.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="stacked-radial"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 200px;
  height: 200px;
}</pre>
</div>

<pre class="brush: css notranslate">.stacked-radial {
  background:
      radial-gradient(circle at 50% 0,
        rgba(255,0,0,.5),
        rgba(255,0,0,0) 70.71%),
      radial-gradient(circle at 6.7% 75%,
        rgba(0,0,255,.5),
        rgba(0,0,255,0) 70.71%),
      radial-gradient(circle at 93.3% 75%,
        rgba(0,255,0,.5),
        rgba(0,255,0,0) 70.71%) beige;
  border-radius: 50%;
}
</pre>

<p>{{ EmbedLiveSample('Stacked_radial_gradients', 200, 200) }}</p>

<h2 id="Using_conic_gradients">Using conic gradients</h2>

<p>The <strong><code>conic-gradient()</code></strong> <a href="/en-US/docs/Web/CSS">CSS</a> function creates an image consisting of a gradient with color transitions rotated around a center point (rather than radiating from the center). Example conic gradients include pie charts and color wheels, but they can also be used for creating checker boards and other intersting effects.</p>

<p>The conic-gradient syntax is similar to the radial-gradient syntax, but the color-stops are placed around a gradient arc, the circumference of a circle, rather than on the gradient line emerging from the center of the gradient, and the color-stops are percentages or degrees: absolute lengths are not valid.</p>

<p>In a radial gradient, the colors transition from the center of an ellipse, outward, in all directions. With conic gradients, the colors transition as as if spun around the center of a circle, starting at the top and going clockwise. Similar to radial gradients, you can position the center of the gradient. Similar to linear gradients, you can change the gradient angle.</p>

<div>
<h3 id="A_basic_conic_gradient">A basic conic gradient</h3>

<p>As with linear and radial gradients, all you need to create a conic gradient are two colors. By default, the center of the gradient is at the 50% 50% mark, with the start of the gradient facing up:</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="simple-conic"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.simple-conic {
  background: conic-gradient(red, blue);
}
</pre>

<p>{{ EmbedLiveSample('A_basic_conic_gradient', 120, 120) }}</p>
</div>

<div>
<h3 id="Positioning_the_conic_center">Positioning the conic center</h3>

<p>Like radial gradients, you can position the center of the conic gradient with keyterms, percentage, or absolute lengths, with the keyword "at"</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="conic-gradient"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.conic-gradient {
  background: conic-gradient(at 0% 30%, red 10%, yellow 30%, #1e90ff 50%);
}
</pre>

<p>{{ EmbedLiveSample('Positioning_the_conic_center', 120, 120) }}</p>
</div>

<div>
<h3 id="Changing_the_angle">Changing the angle</h3>

<p>Like radial gradients, you can position the center of the conic gradient with keyterms, percentage, or absolute lengths, with the keyword "at"</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="conic-gradient"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.conic-gradient {
  background: conic-gradient(from 45deg, red, orange, yellow, green, blue, purple);
}
</pre>

<p>{{ EmbedLiveSample('Changing_the_angle', 120, 120) }}</p>
</div>

<h2 id="Using_repeating_gradients">Using repeating gradients</h2>

<p>The {{cssxref("linear-gradient")}}, {{cssxref("radial-gradient")}}, and {{cssxref("conic-gradient")}} functions don't support automatically repeated color stops. However, the {{cssxref("repeating-linear-gradient")}}, {{cssxref("repeating-radial-gradient")}}, and {{cssxref("repeating-conic-gradient")}} functions are available to offer this functionality.</p>

<p>The size of the gradient line or arc that repeats is the length between the first color stop value and the last color stop length value. If the first color stop just has a color and no color stop length, the value defaults to 0. If the last color stop has just a color and no color stop length, the value defaults to 100%. If neither is declared, the gradient line is 100% meaning the linear and conic gradients will not repeat and the radial gradient will only repeat if the radius of the gradient is smaller than the length between the center of the gradient and the farthest corner. If the first color stop is declared, and the value is greater than 0, the gradient will repeat, as the size of the line or arc is the difference between the first color stop and last color stop is less than 100% or 360 degrees.</p>

<div>
<h3 id="Repeating_linear_gradients">Repeating linear gradients</h3>

<p>This example uses {{cssxref("repeating-linear-gradient")}} to create a gradient that progresses repeatedly in a straight line. The colors get cycled over again as the gradient repeats. In this case the gradient line is 10px long.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="repeating-linear"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.repeating-linear {
  background: repeating-linear-gradient(-45deg, red, red 5px, blue 5px, blue 10px);
}
</pre>

<p>{{ EmbedLiveSample('Repeating_linear_gradients', 120, 120) }}</p>
</div>

<div>
<h3 id="Multiple_repeating_linear_gradients">Multiple repeating linear gradients</h3>

<p>Similar to regular linear and radial gradients, you can include multiple gradients, one on top of the other. This only makes sense if the gradients are partially transparent allowing subsequent gradients to show through the transparent areas, or if you include different <a href="/en-US/docs/Web/CSS/background-size">background-sizes</a>, optionally with different <a href="/en-US/docs/Web/CSS/background-position">background-position</a> property values, for each gradient image. We are using transparency.</p>

<p>In this case the gradient lines are 300px, 230px, and 300px long.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="multi-repeating-linear"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 600px;
  height: 400px;
}</pre>
</div>

<pre class="brush: css notranslate">.multi-repeating-linear {
  background:
      repeating-linear-gradient(190deg, rgba(255, 0, 0, 0.5) 40px,
        rgba(255, 153, 0, 0.5) 80px, rgba(255, 255, 0, 0.5) 120px,
        rgba(0, 255, 0, 0.5) 160px, rgba(0, 0, 255, 0.5) 200px,
        rgba(75, 0, 130, 0.5) 240px, rgba(238, 130, 238, 0.5) 280px,
        rgba(255, 0, 0, 0.5) 300px),
      repeating-linear-gradient(-190deg, rgba(255, 0, 0, 0.5) 30px,
        rgba(255, 153, 0, 0.5) 60px, rgba(255, 255, 0, 0.5) 90px,
        rgba(0, 255, 0, 0.5) 120px, rgba(0, 0, 255, 0.5) 150px,
        rgba(75, 0, 130, 0.5) 180px, rgba(238, 130, 238, 0.5) 210px,
        rgba(255, 0, 0, 0.5) 230px),
      repeating-linear-gradient(23deg, red 50px, orange 100px,
        yellow 150px, green 200px, blue 250px,
        indigo 300px, violet 350px, red 370px);
}
</pre>

<p>{{ EmbedLiveSample('Multiple_repeating_linear_gradients', 600, 400) }}</p>
</div>

<h3 id="Plaid_gradient">Plaid gradient</h3>

<p>To create plaid we include several overlapping gradients with transparency. In the first background declaration we listed every color stop separately. The second background property declaration using the multiple position color stop syntax:</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="plaid-gradient"&gt;&lt;/div&gt;</pre>

<pre class="brush: css notranslate">div {
  width: 200px;
  height: 200px;
}</pre>
</div>

<pre class="brush: css notranslate">.plaid-gradient {
  background:
      repeating-linear-gradient(90deg, transparent, transparent 50px,
        rgba(255, 127, 0, 0.25) 50px, rgba(255, 127, 0, 0.25) 56px,
        transparent 56px, transparent 63px,
        rgba(255, 127, 0, 0.25) 63px, rgba(255, 127, 0, 0.25) 69px,
        transparent 69px, transparent 116px,
        rgba(255, 206, 0, 0.25) 116px, rgba(255, 206, 0, 0.25) 166px),
      repeating-linear-gradient(0deg, transparent, transparent 50px,
        rgba(255, 127, 0, 0.25) 50px, rgba(255, 127, 0, 0.25) 56px,
        transparent 56px, transparent 63px,
        rgba(255, 127, 0, 0.25) 63px, rgba(255, 127, 0, 0.25) 69px,
        transparent 69px, transparent 116px,
        rgba(255, 206, 0, 0.25) 116px, rgba(255, 206, 0, 0.25) 166px),
      repeating-linear-gradient(-45deg, transparent, transparent 5px,
        rgba(143, 77, 63, 0.25) 5px, rgba(143, 77, 63, 0.25) 10px),
      repeating-linear-gradient(45deg, transparent, transparent 5px,
        rgba(143, 77, 63, 0.25) 5px, rgba(143, 77, 63, 0.25) 10px);

  background:
      repeating-linear-gradient(90deg, transparent 0 50px,
        rgba(255, 127, 0, 0.25) 50px 56px,
        transparent 56px 63px,
        rgba(255, 127, 0, 0.25) 63px 69px,
        transparent 69px 116px,
        rgba(255, 206, 0, 0.25) 116px 166px),
      repeating-linear-gradient(0deg, transparent 0 50px,
        rgba(255, 127, 0, 0.25) 50px 56px,
        transparent 56px 63px,
        rgba(255, 127, 0, 0.25) 63px 69px,
        transparent 69px 116px,
        rgba(255, 206, 0, 0.25) 116px 166px),
      repeating-linear-gradient(-45deg, transparent 0 5px,
        rgba(143, 77, 63, 0.25) 5px 10px),
      repeating-linear-gradient(45deg, transparent 0 5px,
        rgba(143, 77, 63, 0.25) 5px 10px);
}
</pre>

<p>{{ EmbedLiveSample('Plaid_gradient', 200, 200) }}</p>

<h3 id="Repeating_radial_gradients">Repeating radial gradients</h3>

<p>This example uses {{cssxref("repeating-radial-gradient")}} to create a gradient that radiates repeatedly from a central point. The colors get cycled over and over as the gradient repeats.</p>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="repeating-radial"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 120px;
  height: 120px;
}</pre>
</div>

<pre class="brush: css notranslate">.repeating-radial {
  background: repeating-radial-gradient(black, black 5px, white 5px, white 10px);
}
</pre>

<p>{{ EmbedLiveSample('Repeating_radial_gradients', 120, 120) }}</p>

<h3 id="Multiple_repeating_radial_gradients">Multiple repeating radial gradients</h3>

<div class="hidden">
<pre class="brush: html notranslate">&lt;div class="multi-target"&gt;&lt;/div&gt;
</pre>

<pre class="brush: css notranslate">div {
  width: 250px;
  height: 150px;
}</pre>
</div>

<pre class="brush: css notranslate">.multi-target {
  background:
      repeating-radial-gradient(ellipse at 80% 50%,rgba(0,0,0,0.5),
        rgba(0,0,0,0.5) 15px, rgba(255,255,255,0.5) 15px,
        rgba(255,255,255,0.5) 30px) top left no-repeat,
      repeating-radial-gradient(ellipse at 20% 50%,rgba(0,0,0,0.5),
        rgba(0,0,0,0.5) 10px, rgba(255,255,255,0.5) 10px,
        rgba(255,255,255,0.5) 20px) top left no-repeat yellow;
  background-size: 200px 200px, 150px 150px;
}
</pre>

<p>{{ EmbedLiveSample('Multiple_repeating_radial_gradients', 250, 150) }}</p>

<h2 id="같이_보기">같이 보기</h2>

<ul>
 <li>Gradient functions: {{cssxref("linear-gradient")}}, {{cssxref("radial-gradient")}}, {{cssxref("conic-gradient")}}, {{cssxref("repeating-linear-gradient")}}, {{cssxref("repeating-radial-gradient")}}, {{cssxref("repeating-conic-gradient")}}</li>
 <li>Gradient-related CSS data types: {{cssxref("&lt;gradient&gt;")}}, {{cssxref("&lt;image&gt;")}}</li>
 <li>Gradient-related CSS properties: {{cssxref("background")}}, {{cssxref("background-image")}}</li>
 <li><a class="external" href="http://lea.verou.me/css3patterns/">CSS Gradients Patterns Gallery, by Lea Verou</a></li>
 <li><a class="external" href="http://standardista.com/cssgradients">CSS3 Gradients Library, by Estelle Weyl</a></li>
 <li><a href="https://cssgenerator.org/gradient-css-generator.html">Gradient CSS Generator</a></li>
</ul>