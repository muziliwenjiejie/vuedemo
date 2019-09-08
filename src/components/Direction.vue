<template>
  <!--<span>消防巡检柜说明书下载</span>-->
  <div>
  <span>变频柜说明视频下载</span>
  <div class="video-box row">
      <video-player class="video-player vjs-custom-skin col-md-6" ref="videoPlayer" :playsinline="true" :options="playerOptions"></video-player>
      <div class="video-list col-md-3">
        <div @click="chooseVideo(videos)" v-for="video in videos" v-bind:key="video.id" class="thumbnail">
          <span>{{ video.name }}</span>
          <span>{{ video.id }}</span>
          <!--<div class="thumbnail-img">
            <img :src="video.thumbnail" :alt="video.title" />
          </div>
          <div class="thumbnail-info">
            <span>{{ video.title }}</span>
            <div class="thumbnail-views">
              <span>{{ video.speaker }}</span>
            </div>
            <div class="thumbnail-describe">{{ video.describe }}</div>
          </div>-->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import VueVideoPlayer from 'vue-video-player'
import 'video.js/dist/video-js.css'
import 'vue-video-player/src/custom-theme.css'
Vue.use(VueVideoPlayer)
export default {
  name: 'bpxjDirection',
  data () {
    let videos = [
      {
        id: 0,
        name: '单速风机',
        type: '',
        src: '../../static/images/mp4/爱剪辑-单速风机.mp4'
      },
      {
        id: 1,
        name: '变频一控二壁挂',
        type: '',
        src: '../static/images/mp4/爱剪辑-变频一控二壁挂.mp4'
      },
      {
        id: 2,
        name: '单速风机',
        type: '',
        src: '../static/images/mp4/爱剪辑-单速风机.mp4'
      },
      {
        id: 3,
        name: '单台+手动落地',
        type: '',
        src: '../static/images/mp4/爱剪辑-单台+手动落地.mp4'
      },
      {
        id: 4,
        name: '双速风机',
        type: '',
        src: '../static/images/mp4/爱剪辑-双速风机.mp4'
      },
      {
        id: 5,
        name: '双台稳压~水泵',
        type: '',
        src: '../static/images/mp4/爱剪辑-双台稳压~水泵.mp4'
      },
      {
        id: 6,
        name: '一控二+控制器落地',
        type: '',
        src: '../static/images/mp4/爱剪辑-一控二+控制器落地.mp4'
      },
      {
        id: 7,
        name: '一控一单台手动壁挂',
        type: '',
        src: '../static/images/mp4/爱剪辑-一控一单台手动壁挂.mp4'
      },
      {
        id: 8,
        name: '双台排污一用一备',
        type: '',
        src: '../static/images/mp4/双台排污一用一备.mp4'
      }
    ]
    return {
      playerOptions: {
        playbackRates: [0.7, 1.0, 1.5, 2.0], // 播放速度
        autoplay: false, // 如果true,浏览器准备好时开始回放。
        muted: false, // 默认情况下将会消除任何音频。
        loop: false, // 导致视频一结束就重新开始。
        preload: 'auto', // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
        language: 'zh-CN',
        aspectRatio: '16:9', // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
        fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
        videos,
        sources: videos[0],
        // poster: '../../static/image/fxpx12.jpg', // 你的封面地址
        // width: document.documentElement.clientWidth,
        notSupportedMessage: '此视频暂无法播放，请稍后再试', // 允许覆盖Video.js无法播放媒体源时显示的默认信息。
        controlBar: {
          timeDivider: true,
          durationDisplay: true,
          remainingTimeDisplay: false,
          fullscreenToggle: true // 全屏按钮
        }
      }
    }
  },
  methods: {
    chooseVideo: function (video) {
      // 设置视频为当前视频
      this.sources = video
      // 视频点浏览器
      console.log(this.sources.src)
      console.log(this.video.name)
      // video.views += 1
    }

  }
}
</script>

<style scoped>

</style>
