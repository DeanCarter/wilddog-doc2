
title: 更新日志
---

## iOS SDK

### V0.4.2 - 2016.11.04

**修复**

MeetingCastAddon中castingParticipantID属性始终为nil的问题。

**优化**

WDGVideoStream不再强引用WDGVideoView，二者可以分别销毁，detach会在销毁前自动执行。

### V0.4.1 - 2016.10.27

**优化**

- 将 SDK 更新为静态库。
- 升级 WebRTC 库版本为 M55。

### V0.4.0 - 2016.10.19

**优化**

- 更新错误码。
- 发起会议等部分接口变更。

### V0.3.4 - 2016.10.14

**修复**

- 增加边界条件限制，API 调用参数错误时会给出提示。

### V0.3.3 - 2016.10.12

**修复**

- `WDGVideoClient` 被销毁后，之前创建的本地流未关闭，重新创建 `WDGVideoClient` 并创建本地流耗时过长。
- iOS10 下，当应用未在 Info.plist 添加麦克风权限导致的崩溃问题。
- 更新 API 文档注释。

### V0.3.2 - 2016.09.29

**修复**

- 视频流的开启、关闭接口改为属性，以使其可查询。
- 接受邀请时增加可指定本地视频流的 API 接口。
- 代理标记为  `nullable` 。
- 增加部分 API 注释。
- 修复 WDGVideoView 的 size 被设为 0 时引发的布局计算问题。

### V0.3.1 - 2016.09.22

**修复**

- ConversationMode 的字符串表示改为 `p2p` 与 `server_based`。
- 本地视频流目前只支持 352x288 640x480 和 1280x720 三种，因此在对外公开的枚举量中去除无效的选项。
- 邀请接口，userID 输入空字符串或 nil ，localStream 输入已关闭的流和 nil 的情况下都回直接返回错误信息，不会将邀请发出去。因此接口的返回值改为 nullable。

### V0.3.0 - 2016.09.22

**新增**

- 新增 Server based 模式。
- 新增 MeetingCast 模块。

**修复**

- 改进本地流创建及销毁策略。
- RTCPeerconnectionFactory 设为单例以避免其早于 LocalStream 等对象销毁。
- WDGVideoView 适用 contentMode 选项，支持 AspectFit 、 AspectFill 和 Fill 三种显示模式。
- WDGVideoConversation 中的邀请API返回值改为 BOOL。
- 修复 WDGVideoConversation 中 participants 只增不减的问题。

</br>

---

## Android SDK

### V0.4.1 - 2016.10.27

**新增**

- 新增视频展示控件 WilddogView。

**优化**

- 升级 WebRTC 库，目前使用 M55 版本。
- 修改 WilddongVideo 类 createLocalStream 方法。
- 增加对视频 H.264 编码的支持。

### V0.4.0 - 2016.10.19

**新增**

- 新增安卓端错误码,增加错误边界判定以及错误返回。
- 新增 VideoException 类。

**优化**

- Video 类改为 WilddogVideo 类。
- MeetingCastAddon 类中方法重命名为 start、switchParticipant、stop。
- MeetingCastListener 中方法重命名 onStarted、onSwitchParticipant、onStopped。
- 删除 ConversationException 类。

### V0.3.1 - 2016.09.29

**新增**

- 增加 Conversation.Listener 回调方法触发。

**优化**


- 完善 Video ，完善 flipCamera方法。
- 完善 Stream，修复 enableAudio/enableVideo 方法。

**修复**

- 修复 Conversation,修复邀请第三方加入会话连接建立失败 bug。

### V0.3.0 - 2016.09.22

**新增**

- 新增 SERVER_BASED 模式会话。
- 新增直播接口，实现直播/切流/断开直播功能。

**修复**

- 修改原有 BASIC 模式为P2P模式，修改 ADVANCED 模式为 SERVER_BASED。
- 修改 getConfig 功能，增加推流/收流地址。

</br>

---

## Javascript SDK

### v0.4.5 - 2016.11.02

**新增**

- 新增对Safari浏览器的支持。

### V0.4.4 - 2016.10.27

**优化**

- 优化代码结构。

### v0.4.3 - 2016.10.22

**新增**

- 新增错误码以及相应的错误事件。

**优化**

- 优化meetingCast 类的接口名称。

### V0.4.2 - 2016.10.13

**修复**

- video.createStream 传入 video 参数为 true 时，不能获取视频流
- 修复后传入 video 参数为 true 时，视频流规格自动设为 standard 标准

### V0.4.1 - 2016.10.10

**优化**

- 压缩 SDK 大小，从 300+K 压缩为 100+K。
- 被邀请方接受邀请后，邀请方的 OutgoingInvite 会触发 promise，得到 Conversation 对象。 

### V0.4.0 - 2016.10.08

**优化**

- 将回调修改为 promise。

### V0.3.3 - 2016.09.30

**修复**

- 修复同一用户退出会话后重新加入会话会读取过期信令的 bug。

### V0.3.2 - 2016.09.29

**修复**

- 修复 server_based 模式下，每当新用户加入 conversation，已有用户都会重复发布视频流的 bug。
- 修复离开 conversation 后还会监听 conversation 中消息的 bug。

