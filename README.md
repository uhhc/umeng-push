# umeng-push

[![GoDoc](https://godoc.org/github.com/uhhc/umeng-push?status.svg)](https://godoc.org/github.com/uhhc/umeng-push)

<a href="https://developer.umeng.com/docs/66632/detail/68343">友盟推送</a>友盟推送服务端SDK,推送相关接口使用HTTPS协议,用户标签相关接口使用HTTP协议(因为官方的HTTPS接口无法访问)

#### 一、快速开始

##### 下载安装
```bash
$ go get -u github.com/uhhc/umeng-push
```

##### 使用示例
```go
package main

import (
	"github.com/uhhc/umeng-push"
	"log"
)

func main() {
	// 初始化客户端
	var appKey = "your app_key"
	var appMasterKey = "your app_master_key"
	umengPush := umeng_push.NewUmengPush(appKey, appMasterKey)

	// 根据业务装填参数
	param := &umeng_push.SendParam{}

	// 请求调用
	result, err := umengPush.Send(param)
	if err != nil {
		log.Fatal(err)
	}
	log.Println(result.Data.TaskId)
}
```

#### 二、已实现接口列表
- 消息发送
- 任务类消息状态查询
- 任务类消息取消
- 文件上传
- 给设备打标签
- 查询设备标签列表
- 设置设备标签
- 删除设备标签
- 清除设备标签
