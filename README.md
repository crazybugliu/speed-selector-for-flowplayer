# speed-selector-for-flowplayer

- 将[flowplayer](https://github.com/flowplayer/flowplayer)的清晰度调整 定制为可在外部获取到`quality-change`事件，以便获取不同清晰度视频的地址然后`load`视频：

  ```javascript
  flowPlayerApi.on('quality-change', function (ev, api, quality) {....});
  ```

- 增加播放速度调整控制：

  ```javascript
      _flowPlayer = flowplayer('#vodsPlayer', {
          clip: {
              sources: [{
                  type: "video/mp4",
                  src: "http://path/to/video.mp4"
              }],
              speedEnable: true,                           //开启播放倍速控制
              speeds:['1', '2', '4'],                      //播放倍速
              qualities: ["流畅", "高清", "超清", "蓝光"],  //清晰度列表
              defaultQuality: "流畅",                      //默认清晰度
          }
      });
  ```

 



效果：![show](show.png)



TODO：

增加功能：使用时只给出获取不同清晰度的callback方法，该方法得到视频地址， 获取到后自动按原参数load到播放器。