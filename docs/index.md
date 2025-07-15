---
hide:
  - navigation
  - toc
  - path
  - pageTitle
  - editButton
glightbox: false  # 禁止图片放大  或者在标签中使用 class="on-glb" 让某一个标签允许放大(off-glb)
---

<style>
  .md-typeset h1,
  .md-content__button {
    display: none;
  }
  .md-content__inner{
    padding-top: 0em;
  }

  /* 默认不修改背景 */
  body {
    background-image: url("../images/home/DSC_2943.JPG");
    background-size: cover;               /* 全屏铺满，保持比例，裁剪多余部分 */
    background-repeat: no-repeat;
    background-position: center center;   /* 水平 & 垂直方向都居中 */
    background-attachment: fixed;         /* 背景固定（可选，可改为 scroll） */
    background-color: #000;               /* 防止加载期间白屏 */
  }

  .md-header,
  .md-footer {
    background: rgba(255, 255, 255, 0);         /* 半透明白色背景 */
    backdrop-filter: blur(1px);                   /* 毛玻璃模糊效果 */
    -webkit-backdrop-filter: blur(1px);           /* Safari 兼容 */
    color: #fff;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);  /*轻微阴影增加立体感 */
  }

  .md-footer-meta {
    background: rgba(255, 255, 255, 0.5);         /* 半透明白色背景 */
    backdrop-filter: blur(3px);                   /* 毛玻璃模糊效果 */
    -webkit-backdrop-filter: blur(3px);           /* Safari 兼容 */
    /* color: #fff; */
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);  /*轻微阴影增加立体感 */
  }

  .md-tabs , [data-md-color-primary=black] .md-header , [data-md-color-primary=black] .md-tabs{
    background-color: transparent;
  }

  .md-copyright__highlight {
    color: #000;
  }

  .md-social__link svg {
    fill: rgb(0 0 0);
  }

  .md-footer, .md-footer-meta { 
  display: block; /* 或者 inline-block / flex，根据你的布局情况 */
  }

  /* 当视口宽度小于1220px时隐藏 */
  @media (max-width: 1219px) {
    .md-footer, .md-footer-meta { 
      display: none;
    }
  }
</style>
<link rel="stylesheet" href="/stylesheets/index.css">

<!--    时间    -->
<div class="time">
<!-- <h2>你现在有多悲伤，就证明你曾经拥有多少爱</h2> -->

  <div class="solar-time" id="solarTime"></div>
  <div class="clock-time">
    <span id="hourTime" class="clock-font">00</span>
    <span class="colon">:</span>
    <span id="minuteTime" class="clock-font">00</span>
    <span class="colon">:</span>
    <span id="secondTime" class="clock-font">00</span>
  </div>
</div>



<!-- 搜索引擎按钮 -->
<div class="search-container" onselectstart="return false">
  <ul class="search-engine-buttons" style="margin-left: 0;display: flex; list-style: none;margin:20px  0 0 0;">
    <li class ="search-englne-text" data-engine="google" style="margin-left: 0px">Google</li>
    <li class ="search-englne-text" data-engine="bing" style="margin-left: 0px">Bing</li>
    <li class ="search-englne-text" data-engine="wikipedia" style="margin-left: 0px">Wikipedia</li>
  </ul>
</div>

<!-- 搜索输入框 -->
<div class="input-container">
  <input type="text" id="search-input" placeholder="选择引擎 回车搜索" class="gradient-input" />
</div>

<script type="text/javascript" src="./javascripts/index.js"></script>

