# spring-quickstart

spring快速入门

> 官网文档: [https://spring.io/quickstart](https://spring.io/quickstart)

## spring

Spring 让每个人都可以更快、更轻松、更安全地编写 Java。Spring 对速度、简单性和生产力的关注使其成为世界上最受欢迎的Java 框架

## 快速入门

- 启动新项目

利用 [start.spring.io](https://start.spring.io/) 创建新项目

![1](/docs/1.jpg)

- 添加代码

在DemoApplication文件,添加代码

```
@RestController
@SpringBootApplication
public class DemoApplication {

	public static void main(String[] args) {
		SpringApplication.run(DemoApplication.class, args);
	}

	@GetMapping("/hello")
	public String hello(@RequestParam(value = "name", defaultValue = "World")String name) {
		return String.format("Hello %s!", name);
	}
}
```

> 注释详解

- @RestController: 告诉Spring这段代码描述了一个应该在 web 上可用的端点
- @GetMapping(“/hello”): 告诉 Spring 使用我们的方法hello()来回答发送到该http://localhost:8080/hello地址的请求
- @RequestParam: 告诉 Springname在请求中期待一个值，但如果它不存在，它将默认使用单词“World”

- 构建并程序

命令行输入

```
// 运行
mvn clean spring-boot:run

// 打包
mvn clean package
```

你可以在浏览器输入 [http://localhost:8080/hello]( http://localhost:8080/hello), 查看结果

![2](/docs/2.jpg)