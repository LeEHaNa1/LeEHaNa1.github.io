---
layout: post
title: HTTP 통신 과정
subtitle: 전반적인 HTTP 통신 과정을 살펴본 후, spring과의 관계에 대해 살펴본다.
tags: [network, spring, HTTP]
comments: true
mathjax: true
author: Lee Hana
---

{: .box-success}
전반적인 HTTP 통신 과정 / Apache와 Apache Tomcat / HTTP 통신 과정에서 spring의 역할 등에 대해 살펴보는 page.


## 전반적인 HTTP 통신 과정

1. 전반적인 HTTP 통신
   - browser가 Apache에게 HTTP 요청을 보냄.
   - Apache가 Tomcat에게 HTTP 요청을 전달함.
   - Tomcat이 Spring Application에게 전달.
   - Spring Application 내부에서 Controller, Service, Model 동작함.
   - Spring Application이 HTTP 응답을 Tomcat에게 전달함.
   - Tomcat이 Apache에게 전달함.
   - Apache가 browser에게 전달하여 HTTP 응답을 받게 됨.


2. 각 요소의 역할(HTTP response 전달 전까지)
    - Apache : Web Server
    - Apache Tomcat : Servlet Container
    - Spring Framework :Java Application Framework


## Apache와 Apache Tomcat

1. Apache와 Apache Tomcat의 차이점
   Apache는 Web Server로 정적인 data 처리하는 server임.
   Apache Tomcat은 Servlet Container(=WAS)로 동적인 data 처리하는 server임.


2. Apache와 Tomcat 연동하여 사용하는 이유
   Web page에는 정적 data와 동적 data가 공존함. Apache는 정적 data 처리에 매우 효율적이며 Tomcat은 동적 data 처리에 매우 효율적임. Apache와 Tomcat을 같이 사용하는 이유는 각자 효율적으로 처리하는 data가 다르기 때문이며 대규모 traffic 분산, load balancing, 보안 계층 분리 등으로 인해서임.

3. Spring Boot 사용 시 Apache 사용하지 않아도 되는 이유
   Spring Boot가 Tomcat 내장하고 있기 때문에 Apache 없이도 Web server, WAS server 역할을 모두 수행할 수 있어 소규모/일반 서비스에서는 충분함. 다만, 대규모 서비스에서는 Spring Boot 내에 Tomcat이 내장되어 있다고 하더라도 처리가 힘들 수 있어서 Apache HTTP server를 앞단에 따로 두어 사용하기도 함.


## HTTP 통신에서 Client Program과 Server Program

1. HTTP 통신의 주체 중 Client Program
   - Browser
   - 예를 들면, Chrome, Safari, Edge 등이 있음.


2. HTTP 통신의 주체 중 Server Program
   - Apache Tomcat
   - Apache Tomcat이 HTTP request 받아 들이는 주체이기 때문.
   - Spring은 Tomcat 위에서 동작하는 Framework.


<details markdown="1">
<summary>Click here!</summary>
Here you can see an **expandable** section
</details>
