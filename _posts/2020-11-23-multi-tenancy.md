---
layout: article
title: 멀티 테넌시 아키텍쳐(Multi Tenancy Architecture)란?
aside:
  toc: true
tags: cloud
published : true
---

# 들어가기 전에
Cloud computing 기술이 보급화 되면서, 비용 효율을 위한 다양한 기술들이 언급되고 있습니다. 그 중 하나인 Multi-tenancy가 무엇인지에 대해 포스팅하고자 합니다.

# 핵심 개념
- 멀티 테넌시 아키텍쳐(Multi Tenancy Architecture)

<!--more-->
# 멀티 테넌시(Multi Tenancy)란?

![Google seach console 접속화면](/assets/../../assets/images/posts/cloud/1/1.png)

멀티 테넌시는 소프트웨어 응용 프로그램의 <mark>단일 인스턴스</mark>가 테넌트(tenants)라고 불리는 <mark>여러 사용자</mark>에게 서비스를 제공하는 아키텍처의 원칙입니다. 멀티 테넌시는 서로 다른 클라이언트 조직에 대해 별도의 소프트웨어 인스턴스가 설정된 다중 인스턴스 아키텍처와 대조됩니다. 멀티 테넌지 아키텍처에서 소프트웨어 응용 프로그램은 데이터와 구성을 가상으로 분할하도록 설계돼, 각 클라이언트 조직은 사용자 정의된 가상 애플리케이션 인스턴스로 작업합니다. 즉 여러 테넌트들은 동일한 저장 메커니즘을 사용하여 동일한 운영체제, 하드웨어에서 실행되는 동일한 애플리케이션을 공유합니다. 단 테넌트는 서로의 데이터를 공유하거나 볼 수 없습니다. 

# 멀티 테넌시 vs 가상화
멀티 테넌시는 전에 설명했듯이 복수의 고객이 동일한 응용 프로그램을 공유합니다. 고객 간의 구별은 응용 프로그램 설계 중에 수행되므로 고객들은 각 고객의 데이터를 보거나 공유하지 못합니다. 이는 구성 요소가 이앙돼 각 고객 애플리케이션이 별도의 가상 머신에서 구동되는 것처럼 보이게 하는 가상화와 비교됩니다. 

# 클라우드 내 멀티 테넌시
클라우드 컴퓨팅에서는 가상화, 컨테이너화, 원격 엑세스를 활용하는 새로운 서비스 모델 때문에 멀티 테넌시 아키텍처의 의미가 확대되었습니다. 단일 테넌트 클라우드에서는 각 테넌트가 소프트웨어 애플리케이션의 전용 인스턴스를 가지고 있습니다. 이에반해, SaaS(Software-as a Service) 제공자는 데이터베이스의 한 인스턴스에서 애플리케이션의 한 인스턴스를 실행하고 여러 고객에게 웹 액세스를 제공할 수 있습니다. 이러한 시나리오에서는 각 테넌트의 데이터가 격리되어 다른 테넌트에게는 보이지 않는 상태를 유지합니다.

# Reference
- [What is Multi Tenancy?](https://networkinterview.com/what-is-multi-tenancy/)


<!--more-->