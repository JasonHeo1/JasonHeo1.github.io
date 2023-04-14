---
layout: post
title: Dubbo MSA Framework
categories: [Java]
description: Dubbo MSA Framework
keywords: Java, Dubbo, MSA
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---

Apache Dubbo는 MSA (Microservices Architecture) 시스템을 위한 RPC (Remote Procedure Call) 프레임워크입니다. MSA는 서비스를 작은 단위로 분리하여 독립적으로 개발, 배포, 운영할 수 있는 아키텍처입니다.

Dubbo의 아키텍처는 크게 3가지 요소로 이루어져 있습니다.

1. Provider
- 서비스를 제공하는 쪽입니다.
- Dubbo는 자바 기반의 프레임워크이기 때문에, Provider는 자바 언어로 작성됩니다.
- 서비스를 개발하고, Dubbo를 이용하여 서비스를 노출합니다.

2. Consumer
- 서비스를 사용하는 쪽입니다.
- Provider와 마찬가지로 자바 언어로 작성됩니다.
- Dubbo를 이용하여 서비스를 호출하고, 결과를 받아옵니다.

3. Registry
- Provider와 Consumer 사이의 중간 매개체입니다.
- Provider가 제공하는 서비스의 정보를 저장하고, Consumer는 이 정보를 이용하여 서비스를 호출합니다.
- Dubbo에서는 Zookeeper, Redis, Nacos 등의 분산형 서비스 레지스트리를 지원합니다.

Dubbo의 아키텍처는 RPC 기반으로 동작합니다. Provider는 Dubbo를 이용하여 서비스를 노출하고, Consumer는 Dubbo를 이용하여 서비스를 호출합니다. Dubbo는 이를 가능하게 하기 위해 다양한 프로토콜과 직렬화 방식을 지원합니다. 또한, 로드 밸런싱, 장애 처리, 분산 트랜잭션 등의 기능을 제공하여 MSA 시스템의 안정성과 확장성을 보장합니다.

![image](https://user-images.githubusercontent.com/31334576/227722226-81eb2a40-06a6-4d89-8e20-f71fa286bcf5.png)
