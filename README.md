# 说明
可读取nacos配置并监听配置变更

# 使用方法
```go
import "github.com/gangaoh/go-nacos"

# 读取配置并监听
nacos.GetString("test2", "test.group", func(data *string, err error) {
  if err == nil {
     fmt.Println("data2:", *data
  } else {
     fmt.Println(err)
  }
})

# 只读取不监听
d, _ := nacos.GetString("test3", "test.group", nil)
fmt.Println(d)

```
# 注意事项
  必须将config文件放置在config文件夹中，config文件夹位于项目根目录。config内容为nacos服务器相关配置。
  
# config内容
  ```json
  {
	"nacos": {
		"ClientConfig": {
			"NamespaceId": "d9fd09cf-6569-1111-a623-11111111111",
			"TimeoutMs": 5000,
			"NotLoadCacheAtStart": true,
			"Username": "gangaoh",
			"Password": "gangaoh"
		},
		"ServerConfig": {
			"IpAddr": "10.10.10.15",
			"ContextPath": "/nacos",
			"Port": 8848,
			"Scheme": "http"
		}
	}
}
  ```
