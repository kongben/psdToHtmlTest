<template>
  <div class="comments_box">
    <div class="comments_title">
      <img class src="../../assets/comments_title.png" alt />
    </div>
    <div class="comments_content">
      <div class="comments_nav">
        <div class="comments_tips">
          <span class="comments_tips_text">直播讨论</span>
          <span class="comments_tips_num">(3678人人参与）</span>
        </div>
        <div class="comments_submit">
          <textarea class="comments_textarea" placeholder="发表评论"></textarea>
          <div class="comments_textarea_submit">发送</div>
        </div>
        <div class="comments_list">
          <Item></Item>
          <Item></Item>
          <Item></Item>
          <Item></Item>
          <Item></Item>
        </div>
        <div class="comments_page">
          <div class="comments_page_item">上一页</div>
          <div class="comments_page_item active">1</div>
          <div class="comments_page_item">2</div>
          <div class="comments_page_item">3</div>
          <div class="comments_page_item">4</div>
          <div class="comments_page_item">5</div>
          <div class="comments_page_item">...</div>
          <div class="comments_page_item">300</div>
          <div class="comments_page_item">下一页</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Item from "./CommentsItem";
export default {
  components: {
    Item
  }
};
</script>

<style scoped>
.comments_box{
  margin-bottom: 123px;
}
.comments_title {
  display: flex;
  justify-content: center;
  margin-top: 73px;
}
.comments_content {
  display: flex;
  justify-content: center;
}
.comments_nav {
  width: 850px;
}
.comments_tips {
  display: flex;
  margin-bottom: 15px;
  border-bottom: 1px solid #e9f4f8;
}
.comments_tips_text {
  font-size: 23px;
  font-family: Microsoft YaHei Regular, Microsoft YaHei Regular-Regular;
  font-weight: 400;
  text-align: left;
  color: #faf5e9;
  line-height: 39px;
}
.comments_tips_num {
  font-size: 16px;
  font-family: Microsoft YaHei Regular, Microsoft YaHei Regular-Regular;
  font-weight: 400;
  text-align: left;
  color: #fbf7ed;
  line-height: 39px;
  letter-spacing: 2px;
  margin-left: 16px;
}
.comments_submit {
  position: relative;
}
.comments_textarea {
  width: 850px;
  height: 161px;
  resize: none;
  outline: none;
  background: #e9f4f8;
  border-radius: 10px;
  margin-bottom: 29px;
  padding: 10px 0 0 46px;
  font-size: 18px;
  font-family: Microsoft YaHei Light, Microsoft YaHei Light-Light;
  font-weight: 300;
  text-align: left;
  color: #959191;
  line-height: 42px;
  box-sizing: border-box;
}
.comments_submit:before {
  content: url(../../assets/input.png);
  position: absolute;
  top: 16px;
  left: 14px;
}

.comments_textarea_submit {
  display: flex;
  justify-content: center;
  width: 90px;
  padding: 10px 0;
  font-size: 18px;
  color: #fff;
  position: absolute;
  top: 117px;
  left: 760px;
  background: #2eced2;
  border-top-left-radius: 10px;
  border-bottom-right-radius: 10px;
  cursor: pointer;
}
.comments_page {
  display: flex;
  justify-content: center;
}
.comments_page_item {
  background: #2eced2;
  border-radius: 2px;
  padding: 6px 11px;
  font-size: 12px;
  font-family: Microsoft YaHei Regular, Microsoft YaHei Regular-Regular;
  font-weight: 400;
  text-align: center;
  color: #ffffff;
  margin-right: 8px;
  cursor: pointer;
}
.active {
  color: #4c4845;
  background: #f7f1df;
  cursor: auto;
}
</style>
