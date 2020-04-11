<template>
  <div class="live_box">
    <div class="live_title">
      <img src="../../assets/live_title.png" alt />
    </div>
    <div class="live_rules">
      <div class="live_rules_left">活动规则：</div>
      <div class="live_rules_right">
        <div>1. 直播期间发表评论的玩家即可获得礼包一个。直播期间将不定时发放各种福利，希望各位玩家积极参与；</div>
        <div>2. 直播中登录此页面的玩家，达到一定的数量，即可解锁相应的礼包，快转发这个页面给自己的游戏好友吧。</div>
      </div>
    </div>
    <div class="live_content">
      <div class="qr_code_box">
        <img src="../../assets/qr_code.png" alt />
      </div>
      <div class="live_player_box">
        <div class="live_player"></div>
      </div>
      <div class="share_bg_box">
        <img class="share_awards" src="../../assets/share.png" alt />
        <img class="comments_awards" src="../../assets/comment.png" alt />
        <SelectItem name="区服:" select_placeholder='最近玩过的区服'></SelectItem>
          <SelectItem name='角色:' select_placeholder='最近玩过的区服'></SelectItem>
          <div class="backTop" @click="backTop"><img src="../../assets/goto_top.png" alt=""></div>
      </div>
    </div>
    <div class="live_process">
      <div class="live_process_tip">
        <span>观看人数达到一定数量后解锁更多礼包，快邀请好友一起来参与吧！</span>
        <img class="live_process_invite" src="../../assets/invite.png" alt />
      </div>
      <div class="live_process_border">
        <div class="live_process_box" :style="{width:processed+'px'}"></div>
        <img
          src="../../assets/process_icon.png"
          :style="{left:processed +'px'}"
          class="process_icon"
          alt
        />
      </div>
      <div class="live_process_num_box">
        <div class="live_process_num_content">
          <div class="live_process_num">500人</div>
          <img class="live_process_btn" src="../../assets/receive_awards.png" alt />
        </div>
        <div class="live_process_num_content">
          <div class="live_process_num">1000人</div>
          <img class="live_process_btn" src="../../assets/receive_awards.png" alt />
        </div>
        <div class="live_process_num_content">
          <div class="live_process_num">1500人</div>
          <img class="live_process_btn" src="../../assets/no_reward.png" alt />
        </div>
        <div class="live_process_num_content">
          <div class="live_process_num">2000人</div>
          <img class="live_process_btn" src="../../assets/receive_awards.png" alt />
        </div>
        <div class="live_process_num_content">
          <div class="live_process_num">3000人</div>
          <img class="live_process_btn" src="../../assets/receive_awards.png" alt />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SelectItem from "./select";
export default {
  components: {
    SelectItem
  },
  data() {
    return {
      process: 200
    };
  },
  computed: {
    processed() {
      return 990 / (1000 / this.process);
    }
  },
  methods: {
     // 点击图片回到顶部方法
  backTop () {
        document.documentElement.scrollTop = 0
  },
  },
  mounted() {
    this.timer = setInterval(() => {
      if (this.process < 1000) {
        this.process++;
      } else {
        this.process = 0;
      }
    }, 10);
  },
  beforeDestroy() {
    clearInterval(this.timer);
  }
}
</script>

<style scoped>
.live_title {
  display: flex;
  justify-content: center;
  margin: 78px 0 23px 0;
}
.live_rules {
  display: flex;
  justify-content: center;
  font-size: 18px;
  font-family: Microsoft YaHei Regular, Microsoft YaHei Regular-Regular;
  font-weight: 400;
  text-align: left;
  color: #234265;
  line-height: 26px;
  letter-spacing: 2px;
  margin-bottom: 17px;
  margin-left: -85px;
}
.live_rules_right {
  flex-direction: row;
  width: 556px;
}
.live_content {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 17px;
}
.qr_code_box {
  margin: -100px 26px 0 0;
}
.live_player_box {
  background: url(../../assets/live_bg.png) no-repeat top center;
  height: 509px;
  width: 743px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.live_player {
  width: 704px;
  height: 396px;
  background-color: #000;
}
.live_player:after {
  content: url("../../assets/live_right.png");
  position: relative;
  top: 330px;
  left: 538px;
  z-index: 2;
}
.live_player:before {
  content: url("../../assets/live_left.png");
  position: relative;
  z-index: 2;
}
.share_bg_box {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: -80px 0 0 25px;
  padding-top: 34px;
  background: url(../../assets/share_bg.png) no-repeat top center;
  width: 185px;
  height: 276px;
}
.share_awards,
.comments_awards {
  width: 156px;
  margin-bottom: 7px;
  cursor: pointer;
  -webkit-user-drag: none;
}
.backTop{
  cursor: pointer;
  margin-top: 10px;
}
.live_process {
  display: flex;
  align-items: center;
  flex-direction: column;
}
.live_process_tip {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 18px;
  font-family: Microsoft YaHei Regular, Microsoft YaHei Regular-Regular;
  font-weight: 400;
  text-align: left;
  color: #fbf6e7;
  line-height: 26px;
  letter-spacing: 2px;
  margin-bottom: 33px;
}
.live_process_invite {
  cursor: pointer;
}
.live_process_border {
  display: flex;
  align-items: center;
  position: relative;
  width: 1000px;
  background-image: url("../../assets/process_border.png");
  height: 29px;
  z-index: 4;
}
.live_process_border::before {
  content: url(../../assets/finish_icon.png);
  position: absolute;
  left: 981px;
  top: 3px;
  z-index: 5;
}
.live_process_box {
  display: flex;
  justify-content: center;
  z-index: 3;
  overflow: hidden;
  background: url(../../assets/process_bar.png) no-repeat top left;
  height: 23px;
  margin-left: 6px;
}
.process_icon {
  position: absolute;
  z-index: 6;
  margin-top: 3px;
}
.live_process_num_box {
  display: flex;
  width: 1000px;
  justify-content: space-between;
}
.live_process_num_content {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 11px;
}
.live_process_num {
  font-size: 16px;
  font-family: Microsoft YaHei Regular, Microsoft YaHei Regular-Regular;
  font-weight: 400;
  text-align: left;
  color: #fff;
  line-height: 26px;
  letter-spacing: 2px;
  margin-bottom: 14px;
}
.live_process_btn {
  cursor: pointer;
}
</style>
