##  SpringCloud入门实例    
####  1、SpringCloud与微服务介绍 
1.1 什么是微服务？     
微服务架构是一种架构模式，它提倡将单一应用程序划分成一组小的服务，服务之间互相协调、互相配合，为用户 提供最终价值。      
每个服务运行在其独立的进程中，服务与服务间采用轻量级的通信机制互相沟通（通常是基于HTTP 的RESTful API）。       
每个服务都围绕着具体业务进行构建，并且能够被独立地部署到生产环境、类生产环境等。另 外，应尽量避免统一的、集中式的服务管理机制，对具体的一个服务而言，应根据业务上下文，选择合适的语言、 工具对其进行构建。    

1.2 SpringCloud     
SpringCloud是微服务框架，是spring旗下的项目之一。其核心思想就是分布式应用，专门为高并发、高负载、高 可用（即所谓的三高系统）而生。    
其思想同大数据技术的分布式计算概念相同，将真正的分布式技术引入web系统 中，达到可伸缩、可配置、持续集成、无缝整合的目的。是当下web开发领域中非常火热的开发技术。    
其主要涉及 配置管理、服务发现、智能路由、负载均衡、熔断处理、控制总线、集群状态管理等等功能。核心组件包括 netflix、zuul、ribbon、feign和hystrix。     
简而言之，SpringCloud是分布式微服务架构下的一站式解决方案，是各个微服务架构落地技术的集合体，俗称微 服务全家桶。      

####  2、SpringCloud与SpringBoot关系    
SpringBoot专注于快速方便的开发单个个体微服务。     
SpringCloud是关注全局的微服务协调、整理、治理的框架，它将SpringBoot开发的单体整合并管理起来。     
SpringBoot可以离开SpringCloud独立使用开发项目，但是SpringCloud离不开SpringBoot，属于依赖关系。       

####  3、Eureka注册中心
eureka是一个高可用的组件，它没有后端缓存，每一个实例注册之后需要向注册中心发送心跳，在默认情况下erureka server也是一个eureka client，必须要指定一个 server。        

当client向server注册时，它会提供一些元数据，例如主机和端口，URL，主页等。Eureka server 从每个client实例接收心跳消息。 如果心跳超时，则通常将该实例从注册server中删除。       

注解@EnableEurekaClient 表明自己是一个eurekaclient（注册客户端）.               
注解@EnableEurekaServer 表明自己是一个eurekaserver (注册服务端)       

官方文档：https://spring.io/guides/gs/service-registration-and-discovery/
