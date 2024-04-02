---
layout: default
title: 2. ECS 용량공급자
nav_order: 20
permalink: docs/02_Tech/AWS/ECS/ecs-capacity-provider
parent: AWS
grand_parent: Tech
---

# ECS 용량공급자
{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# 

{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 글을 쓴 배경

ECS 서비스를 이용해 sample application 도커 이미지를 배포하는 방법을 공유합니다.

## 글 요약


## 시작하기 전

참고자료 [AWS ECS Workshop](https://catalog.us-east-1.prod.workshops.aws/workshops/8c9036a7-7564-434c-b558-3588754e21f5/ko-KR/02-setup/01-atevent)

---

## 1. 용량공급자란

Amazon Elastic Container Registry(ECR)에 ECS에서 실행되는 애플리케이션 이미지를 저장 및 관리할 수 있습니다. 

ECS TaskDefinition에 Amazon ECR 리포지토리를 지정하기만 하면 Amazon ECS에서 지정된 이미지를 가져와 배포합니다.

![img-1.png](img-1.png)

우선, 배포할 이미지를 업로드 해줍니다. 저는 nginx container 이미지를 업로드해주었습니다.

![img-2.png](img-2.png)

참고자료 : [Amazon ECR](https://catalog.us-east-1.prod.workshops.aws/workshops/8c9036a7-7564-434c-b558-3588754e21f5/ko-KR/03-console/03-ecr)

## 2. AWS ECS Cluster 에서 용량공급자 선택하기