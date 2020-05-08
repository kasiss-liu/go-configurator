### go-configurator 配置加载器
[历史版本源码位置](https://github.com/kasiss-liu/go-tools/tree/master/load-config)

- 解析加载 ```.ini```文件
- 解析加载 ```.json```文件
- 解析加载 ```.yml/.yaml```文件


#### usage
```go
config := New("test", "./test/conf.ini")

	homePage, err := config.Get("homePage").String()
	if err == nil {
		fmt.Println(homePage)
	} 

	name, err := config.Get("author").Get("name").String()
	if err == nil {
		fmt.Println(name)
    } 
    
	age, err := config.Get("author").Get("age").Int()
	if err == nil {
		fmt.Println(age)
	} 

	per, err := config.Get("author").Get("percentage").Float64()
	if err == nil {
		fmt.Println(per)
	}

	arr, err := config.Get("author").Get("keywords").ArrayString()
	if err == nil {
		fmt.Println(arr)
    } 
    
	// Output:
	//	https://github.com/kasiss-liu
	//	kasiss
	//	28
	//  0.1
	//	[kasiss liu]

```