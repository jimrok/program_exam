## akka的编程题

###说明
这个题目需要开发人员去了解akka的框架，编程模型，然后在有效的时间内拿出一个可以运行的程序。
1. 首先，akka是有java的编程接口的。所以，代码完全可以用java来完成，不必先去学习scala的语法。
2. 对于使用过akka的人员，本测试题也许不太公平，但从一个方面来说，这样的人热爱技术，热爱编程，是我们追逐的人才。
3. 对于没有学习过akka的人，同样，这道编程题会检查你们对框架的理解，对未知技术，未知问题的独立解决能力，所以，尽快提交你们的成果，好让我判断你们的能力。


###题目

1. 编写一个可以运行的程序，使用akka的Actor完层这个实现。系统的Actor由两类，MasterActor和WorkerActor，MasterActor负责分发任务，WorkerActor负责执行这些任务，他们完成之后，报告结果给MasterActor，最后MasterActor会将最后的结果输出出来。

2. WorkerActor的任务就是接受一个url，这个url是一个开放的web网页地址，例如："https://www.baidu.com", WorkerActor访问这个url，得到这个url对应的网页字节数。
3. 可以不用写任何的配置文件，你可以写死一个url列表。这个测试不会在意你扩展性多好。
4. 请不要扩散这个测试题，我们不是什么大厂，你学到知识就好了。


给一个代码，可以做main函数。

```java
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		List<String> urls = Arrays.asList("https://baidu.com",
				"https://taobao.com", "http://www.csdn.com",
				"http://www.ctrip.com", "https://hao123.com");

		// Manger得到url的列表，然后再传递给WorkerActor。WorkerActor执行url的网页的抓取，把每个网页的bytes值发送给ManagerActor.
		// Mananger最后输出，一共5个网页，共计xxx bytes.
		ManagerActor.getReference().tell(urls, ActorRef.noSender());
		Thread.sleep(20000); // 等待ManagerActor输出最后的结果.

	}
	
```
