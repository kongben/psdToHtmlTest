<template>
  <div class="title_box">
    <div class="title">
      <img src="../assets/logo.png" alt srcset />
      <img class="index-btn" src="../assets/index-btn.png" alt />
    </div>
    <div class="countdown_box">
      <div class="countdown_left">
        <span class="countdown_text">直播倒计时：</span>
        <div class="countdown_border"></div>
      </div>
      <div class="countdown_right">
        <div class="countdown_num_box">
          <span class="countdown_num">{{countDownData.day}}</span>
          <span class="countdown_num">{{countDownData.hou}}</span>
          <span class="countdown_num">{{countDownData.min}}</span>
          <span class="countdown_num">{{countDownData.sec}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      countDownData: {},
      actEndTime: "2020-04-19 18:50:00"
    };
  },
  created() {
    this.countDown();
  },
  beforeDestroy() {
    clearInterval(this.countDownTimer);
  },
  methods: {
    timeFormat(param) {
      return param < 10 ? "0" + param : param;
    },
    countDown() {
      this.countDownTimer = setInterval(() => {
        // 获取当前时间，同时得到活动结束时间数组
        let newTime = new Date().getTime(); // 对结束时间进行处理渲染到页面
        let endTime = new Date(this.actEndTime).getTime();
        let obj = null; // 如果活动未结束，对时间进行处理
        if (endTime - newTime > 0) {
          let time = (endTime - newTime) / 1000; // 获取天、时、分、秒
          let day = parseInt(time / (60 * 60 * 24));
          let hou = parseInt((time % (60 * 60 * 24)) / 3600);
          let min = parseInt(((time % (60 * 60 * 24)) % 3600) / 60);
          let sec = parseInt(((time % (60 * 60 * 24)) % 3600) % 60);
          obj = {
            day: this.timeFormat(day),
            hou: this.timeFormat(hou),
            min: this.timeFormat(min),
            sec: this.timeFormat(sec)
          };
        } else {
          // 活动已结束，全部设置为'00'
          obj = {
            day: "00",
            hou: "00",
            min: "00",
            sec: "00"
          };
        }
        this.countDownData = obj;
      }, 1000);
    }
  }
};
</script>

<style scoped>
.title {
  display: flex;
  justify-content: space-between;
  padding: 28px 360px 0 338px;
  margin-bottom: 334px;
}
.index-btn {
  margin-top: 19px;
  height: 42px;
}
.countdown_text {
  height: 32px;
  font-size: 32px;
  font-family: FZCSJW;
  font-weight: -GB1-0;
  text-align: center;
  color: #ffde77;
  letter-spacing: -1px;
}
.countdown_num_box {
  margin-left: -47px;
}
.countdown_num {
  font-size: 72px;
  font-family: SourceHanSerifCN Heavy, SourceHanSerifCN Heavy-Heavy;
  font-weight: 800;
  text-align: left;
  color: #ffde77;
  margin-right: 35px;
}
.countdown_border {
  width: 168px;
  height: 2px;
  background: #ffde77;
}
.countdown_box {
  display: flex;
  justify-content: center;
}
.countdown_left {
  margin: 35px 59px 0 0;
}
.countdown_right {
  width: 402px;
  height: 78px;
  background: url(../assets/countdown.png) no-repeat top center;
}
</style>
