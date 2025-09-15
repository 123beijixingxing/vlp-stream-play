# vlp-stream-play
# 1. 模块概述
####  vPD.js 是一个基于 Web 技术的视频播放控制类， 是一个基于 WebSocket 和 MediaSource API 的视频播放处理模块，主要用于实现视频流的接收、解码和播放功能。该模块支持多种播放模式（直播、点播、快进、慢放等）和视频编解码格式（H.264/H.265）。

# 2. 核心功能
##  2.1 视频播放处理
#### 初始化播放参数
#### 创建 iframe 容器
#### 生成唯一标识 UUID
#### 设置播放参数（服务器地址、项目ID、频道ID、流类型等）
#### ‌播放状态管理‌：处理播放、暂停、停止等操作
#### ‌播放速率控制‌：支持快进、慢放和正常速度播放

## 2.2 WebSocket 连接管理
#### ‌建立连接‌：根据当前协议自动选择 ws/wss，建立与服务器的 WebSocket 连接
#### 发送请求：发送播放控制指令（播放、暂停、快进等）
#### 消息处理‌：处理连接打开、消息接收、连接关闭等事件
#### API 映射‌：定义各种播放控制操作的 API 名称

## 2.3 媒体流处理
#### 使用 MediaSource API 处理视频流
#### 检测视频编解码器类型
#### 管理 SourceBuffer 和视频缓冲区
#### 处理视频流数据的分段和拼接

# 3. 主要类方法
## 3.1 播放相关方法
# <img width="730" height="364" alt="image" src="https://github.com/user-attachments/assets/830f539a-bb0d-45d1-bc7f-cc433cf40037" />
## 3.2 WebSocket 相关方法
# <img width="722" height="265" alt="image" src="https://github.com/user-attachments/assets/e754f5d6-14fa-4bac-9299-bd31b8d9b55d" />
## 3.3 媒体流处理相关方法
# <img width="725" height="222" alt="image" src="https://github.com/user-attachments/assets/1835612f-2daa-4f48-86d9-7b0ad43c2e07" />
# 4. 数据结构
## 4.1 视频信息对象结构
# <img width="723" height="803" alt="image" src="https://github.com/user-attachments/assets/a99c695a-dea4-4096-95cc-e9fd12f9df2a" />
# 5. 使用示例
## 5.1 初始化播放
# <img width="721" height="303" alt="image" src="https://github.com/user-attachments/assets/2fe84e55-f08e-4e1a-a5bc-7eab6abf67b1" />
## 5.2 建立WebSocket连接
# <img width="724" height="204" alt="image" src="https://github.com/user-attachments/assets/10fd3e50-e3c0-47be-a2f5-251ed6242047" />
## 5.3 控制播放
# <img width="722" height="438" alt="image" src="https://github.com/user-attachments/assets/16b907e5-d5df-4104-a5e5-bef0a35c98c6" />
# 6. 销毁清理
### 使用完毕后应调用 destroy 方法清理资源：
# <img width="732" height="108" alt="image" src="https://github.com/user-attachments/assets/e06769af-496f-4953-bffd-e98f8b9c861a" />
### 该方法会：
#### 中止 SourceBuffer
#### 结束 MediaSource 流
#### 释放视频对象 URL
#### 清理相关资源

# 7. 注意事项
#### 模块依赖 uuidjs 库生成唯一标识
#### 需要配合 vCT.js 模块进行视频编解码检测
#### 使用前需确保浏览器支持 MediaSource API
#### 直播和点播使用不同的 SourceBuffer 模式
#### 需要合理设置缓冲区大小以避免内存问题

# 8. 兼容性说明
#### 支持 H.264 和 H.265 编码格式
#### 自动检测浏览器支持的 MIME 类型
#### 支持 HTTPS 和 HTTP 协议下的 WebSocket 连接
#### 提供多种播放控制功能（播放、暂停、快进、慢放等）
#### 该模块为视频播放提供了完整的解决方案，从连接建立到流媒体处理再到播放控制，涵盖了视频播放的各个环节。
