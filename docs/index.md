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
    font-size: 0px;
    color: rgb(0,0,0,0);
    line-height: 0;
    margin: 0 0 0 0;
  }

  .md-content__inner{
    padding-top: 0em;
  }

  /* 默认不修改背景 */
  /* body {
    background-image: url("../images/home/DSC_2943.JPG");
    background-size: cover;              
    background-repeat: no-repeat;
    background-position: center center;  
    background-attachment: fixed;        
    background-color: #000;              
  }

  .md-header,
  .md-footer {
    background: rgba(255, 255, 255, 0);      
    backdrop-filter: blur(1px);               
    -webkit-backdrop-filter: blur(1px);       
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0); 
  }

  .md-footer-meta {
    background: rgba(255, 255, 255, 0.5);
    backdrop-filter: blur(3px);           
    -webkit-backdrop-filter: blur(3px);   
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0);
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
  display: block; 
  } */

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
    <li class ="search-englne-text" data-engine="CN2EN" style="margin-left: 0px">CN2EN</li>
    <li class ="search-englne-text" data-engine="EN2CN" style="margin-left: 0px">EN2CN</li>
  </ul>
</div>

<!-- 搜索输入框 -->
<div class="input-container">
  <input type="text" id="search-input" placeholder="选择引擎 回车搜索" class="gradient-input" />
</div>

<script type="text/javascript" src="./javascripts/index.js"></script>

