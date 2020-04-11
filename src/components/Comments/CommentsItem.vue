<template>
  <div class="comments_item">
    <div class="avatar">
      <img src="../../assets/avatar.png" alt />
    </div>
    <div class="comments_box">
      <div class="comments_name">沙城*主宰</div>
      <div class="comments_content">这个直播挺有意思的！红月传说越办越好啦！</div>
    </div>
    <div class="comments_time">2020年02月15日 14:59</div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.comments_item {
  display: flex;
  height: 110px;
  border-bottom: 1px solid #f7f1df;
  margin-bottom: 26px;
}
.comments_box {
  flex: 1;
  margin-left: 16px;
}
.comments_name {
  font-size: 16px;
  font-family: Microsoft YaHei Light, Microsoft YaHei Light-Light;
  font-weight: 300;
  text-align: left;
  color: #ffebad;
}
.comments_content {
  font-size: 16px;
  font-family: Microsoft YaHei Light, Microsoft YaHei Light-Light;
  font-weight: 300;
  text-align: left;
  color: #ffffff;
  line-height: 21px;
}
.comments_time {
  font-size: 12px;
  font-family: Microsoft YaHei Light, Microsoft YaHei Light-Light;
  font-weight: 300;
  text-align: left;
  color: #fdfed6;
  line-height: 42px;
  letter-spacing: 1px;
}
</style>
