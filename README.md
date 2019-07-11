# vlog

## vlog 需求分析

- 首页
  - 关注
    - 列表用户元素
      - 用户昵称
      - 用户头像
      - 视频标题
      - 缩略视频图
      - 获赞数
      - 评论数
      - 分享数
    - 功能按钮
      - 点赞
      - 评论
      - 分享
      - 举报
      - 保存
    - 查看用户主页
      - 用户头像
      - 用户昵称
      - 用户城市
      - 用户签名
      - 关注数
      - 获赞数
      - TA 的作品
  - 推荐（与关注一样）
- 视频制作
  - 上传
    - 上传文件
  - 视频编辑
    - 搜搜&添加音乐
    - 播放速度
    - 剪辑
    - 滤镜
  - 拍摄
- 我
  - 登录&修改密码
  - 我的头像
  - 昵称
  - 关注数
  - 粉丝数
  - 分享主页
  - 我的作品
  - 邀请好友
  - 更多
    - 钱包
- 发现
  - 搜素关键字
  - 邀请好友
  - 附近好友

## 系统原型

- 视频上传
- 观看视频
- 作品列表

- Web/App ------上传视频----> 上传服务器 ------> 存储 ------> 下载服务器 --- 下行视频 ------> Web/App

## 接口设计

- vlog 播放接口
  - 接口描述：获取一条 vlog 视频
  - 接口方法：GET
  - 请求地址：http://vlog.com/video/{video_name.mp4}
  - 状态码：200
- vlog 上传接口
  - 接口描述：上传一条 vlog 视频
  - 接口方法：POST multipart/form-data (默认：x-www-form-urlencode, form-data, application/json, text/xml)
    - x-www-form-urlencode 三个字表示非 ASCII 编码的字符
  - 请求地址：http://api.com/api/upload
  - 请求参数：参数名：uploadFile 类型：file
  - 返回状态：成功：200 | 失败：500
- 我的 vlog 列表接口
  - 接口描述：查看 vlog 列表
  - 接口方法：GET
  - 请求地址：http://api.com/api/list
  - 返回状态：成功：200 | 失败：500
  - 返回参数：{"http://doain/static/video1.mp4","http://doain/static/video1.mp4"}

### 项目难点

- 过大文件上传（服务器 IO 负载）
- 视频文件校验（视频内容）
- 文件存储
