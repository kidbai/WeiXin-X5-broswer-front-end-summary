## 前言

之前和现在都有在做微信H5相关的开发，遇到过很多坑的地方，也准备把自己遇到坑的地方写下来，以表示对X5的不满...（逃..

### Android下通过监听loadedmetadata无法获取video相关属性(duration、currentTime等)

原因：目前只会预加载视频数据，不会去解码获取视频信息，解码需要走播放器解码流程，对于Android来说有些重，低端甚至中高端机子会存在卡顿，不少场景用户打开视频不一定会看，于是微信团队剔除了Android解码视频的这么一个流程

如何获取：
- ios下文档加载完，监听*loadedmetadata*
- Android下要待video执行play之后，去监听*durationchange*便可获取
