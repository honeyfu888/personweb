<template>
  <div class="container">
    <div class="btn"><a href="#">我要点赞</a></div>
    <div class="btn"><a href="#">我要关注</a></div>
    <div class="btn"><a href="#">我要评论</a></div>
  </div>
</template>
<style scoped>
.container {
  height: 100%;
  background: linear-gradient(200deg, #2b5876, #033557);
  /* 弹性布局 */
  display: flex;
  /* 允许换行 */
  flex-wrap: wrap;
  /* 将元素靠边对齐 */
  justify-content: space-around;
}
.container .btn {
  position: relative;
  width: 200px;
  height: 60px;
  margin: 30px;
}
.container .btn a {
  /* 绝对定位 */
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  /* 透明度为0.05的白色背景 */
  background: rgba(255, 255, 255, 0.05);
  /* 阴影 */
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
  /* 上下边框 */
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  /* 圆角 */
  border-radius: 30px;
  color: #fff;
  z-index: 1;
  font-weight: 400;
  /* 字间距 */
  letter-spacing: 1px;
  /* 去下划线 */
  text-decoration: none;
  /* 动画过渡 */
  transition: 0.5s;
  /* 溢出隐藏 */
  overflow: hidden;
  /* 背景模糊 */
  backdrop-filter: blur(15px);
}
.container .btn:hover a {
  letter-spacing: 5px;
}
/* 制作扫光效果 */
.container .btn a::before {
  content: "";
  /* 绝对定位 */
  position: absolute;
  top: 0;
  left: 0;
  width: 50%;
  height: 100%;
  /* 渐变背景 透明到白色 */
  background: linear-gradient(to right, transparent, rgba(255, 255, 255, 0.15));
  /* 沿X轴倾斜45度，向右平移0像素 */
  transform: skewX(45deg) translateX(0);
  transition: 0.5s;
}
.container .btn:hover a::before {
  /* 沿X轴倾斜45度，向右平移200% */
  transform: skewX(45deg) translateX(200%);
}
/* 制作按钮上下两个发光层 */
.container .btn::before,
.container .btn::after {
  content: "";
  /* 绝对定位，横向居中 */
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: 40px;
  height: 10px;
  /* 自定义颜色属性--c, 可通过var函数调用 */
  /* --c: gold; */
  background: var(--c);
  border-radius: 5px;
  box-shadow: 0 0 5px var(--c), 0 0 15px var(--c), 0 0 30px var(--c),
    0 0 60px var(--c);
  transition: 0.5s;
}
.container .btn::before {
  bottom: -5px;
}
.container .btn::after {
  top: -5px;
}
.container .btn:hover::before,
.container .btn:hover::after {
  height: 50%;
  width: 80%;
  border-radius: 15px;
  transition-delay: 0.3s;
}
.container .btn:hover::before {
  bottom: 0;
}
.container .btn:hover::after {
  top: 0;
}
/* 分别设置自定义颜色属性--c */
.container .btn:nth-child(1)::before,
.container .btn:nth-child(1)::after {
  --c: #12c2e9;
}
.container .btn:nth-child(2)::before,
.container .btn:nth-child(2)::after {
  --c: #c471ed;
}
.container .btn:nth-child(3)::before,
.container .btn:nth-child(3)::after {
  --c: #f64f59;
}
</style>
