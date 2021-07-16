# flutter_openim_sdk

A Flutter im plugin.

##### [Android体验包(密码：123456)](https://www.pgyer.com/openim)
##### [demo地址](https://github.com/hrxiang/OpenIMFlutterDemo.git)
##### [SDK文档地址](xxxx)

## Getting Started


#### 1，在yaml里添加依赖

      flutter_openim_sdk:
         git:
            url: https://github.com/OpenIMSDK/Open-IM-SDK-Flutter.git
       
#### 2，导入package

      import 'package:flutter_openim_sdk/flutter_openim_sdk.dart';

### Usage

#### 初始化
  
    var msgListener = AdvancedMsgListener();
    
    /// 初始化SDK
    OpenIM.iMManager
      ..initSDK(
        platform: 0,
        ipApi: 'Api接口地址',
        ipWs: 'WebSocket地址',
        dbPath: '数据库目录',
        listener: new InitSDKListener(),
      )

      /// 添加消息监听(移除消息监听: OpenIM.iMManager.messageManager.removeAdvancedMsgListener(msgListener))
      ..messageManager.addAdvancedMsgListener(msgListener)

      /// 设置发送消息进度监听
      ..messageManager.setMsgSendProgressListener(MsgSendProgressListener())

      /// 设置好友关系监听
      ..friendshipManager.setFriendshipListener(FriendshipListener())

      /// 设置会话监听
      ..conversationManager.setConversationListener(ConversationListener())

      /// 设置群监听
      ..groupManager.setGroupListener(GroupListener());
      
#### 会话管理：
      OpenIM.iMManager.conversationManager

#### 好友关系管理：
      OpenIM.iMManager.friendshipManager

#### 消息管理：
      OpenIM.iMManager.messageManager
        
#### 组管理：
      OpenIM.iMManager.groupManager
