---
layout: post
title: Dubbo와 Eureka MSA 프레임웍의 차이점
categories: [Java]
description: Dubbo와 Eureka MSA 프레임웍의 차이점
keywords: Java, Dubbo, MSA
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---

Apache Dubbo와 Netflix Eureka는 모두 MSA (Microservices Architecture) 시스템에서 사용되는 분산형 서비스 디스커버리 프레임워크입니다. 하지만 두 프레임워크는 몇 가지 차이점이 있습니다.

1.프로토콜
- Dubbo는 RPC (Remote Procedure Call) 프로토콜을 사용합니다.
- Eureka는 REST (Representational State Transfer) 프로토콜을 사용합니다.

2.기능
- Dubbo는 로드 밸런싱, 장애 처리, 분산 트랜잭션 등 다양한 기능을 제공합니다.
- Eureka는 서비스 디스커버리 외에는 추가적인 기능을 제공하지 않습니다.

3.언어
- Dubbo는 자바 기반의 프레임워크이며, 자바 언어로 작성된 Provider와 Consumer를 지원합니다.
- Eureka는 언어에 종속되지 않으며, REST 프로토콜을 사용하는 어떤 언어로든 서비스를 등록할 수 있습니다.

4.라이센스
- Dubbo는 Apache 라이센스로 배포됩니다.
- Eureka는 Netflix의 OSS (Open Source Software) 라이센스로 배포됩니다.

따라서, Dubbo는 더 많은 기능과 자바 언어를 지원하는 RPC 프레임워크이고, Eureka는 더 간단한 REST 프로토콜을 사용하는 언어에 종속되지 않는 서비스 디스커버리 프레임워크입니다. 
선택은 사용하고자 하는 기능과 언어에 따라 달라질 수 있습니다.
