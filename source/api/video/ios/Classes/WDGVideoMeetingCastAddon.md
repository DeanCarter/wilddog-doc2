title: WDGVideoMeetingCastAddon
---

MeetingCast 插件，用于控制会话的直播状态。

## 属性

### conversation

**定义**

```objectivec
@property (readonly, strong, nonatomic) WDGVideoConversation *_Nonnull conversation;
```

**说明**

与直播插件关联的会话实例。

</br>

---

### meetingCastStatus

**定义**

```objectivec
@property (readonly, assign, nonatomic) WDGVideoMeetingCastStatus meetingCastStatus;
```

**说明**

表明当前直播的状态。

</br>

---

### castingParticipantID

**定义**

```objectivec
@property (readonly, strong, nonatomic, nullable) NSString *castingParticipantID;
```

**说明**

表明当前正在直播的参与者的 Wilddog ID 。若当前没在直播，该属性为 nil 。

</br>

---

### delegate

**定义**

```objectivec
@property (readwrite, nonatomic, nullable) id<WDGVideoMeetingCastAddonDelegate>delegate;
```

**说明**

符合 [WDGVideoMeetingCastAddonDelegate](../Protocols/WDGVideoMeetingCastAddonDelegate.html) 协议的代理，负责处理直播相关的事件。

</br>

---

## 方法

### -startWithParticipantID:

**定义**

```objectivec
- (void)startWithParticipantID:(nonnull NSString *)participantID;
```

**说明**

开启直播。

**参数**

 参数名 | 说明 
---|---
participantID|开启直播，并直播 Wilddog ID 为 participantID 的参与者。

</br>

---

### -switchToParticipantID:

**定义**

```objectivec
- (void)switchToParticipantID:(nonnull NSString *)participantID;
```

**说明**

在直播开启后，切换直播视频流。

**参数**

 参数名 | 说明 
---|---
participantID|直播 Wilddog ID 为 participantID 的参与者。

</br>

---

### -stop

**定义**

```objectivec
- (void)stop;
```

**说明**

关闭直播。

</br>

---

## 常量

### WDGVideoMeetingCastStatus

**说明**

代表当前直播状态

- WDGVideoMeetingCastStatusClosed: 表示直播未开启或已关闭
- WDGVideoMeetingCastStatusOpen:   表示直播正在进行中
