---
layout: default
title: 1. ECS
nav_order: 1
permalink: docs/02_Tech/AWS/ECS
parent: AWS
grand_parent: Tech
---

# Color Utilities
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

# AWS EC2에서 Docker를 사용하여 Jenkins 배포하기

AWS EC2 인스턴스에 Docker를 사용하여 Jenkins를 배포하는 방법을 공유합니다.

{: .no_toc }
![img.png](img.png)

## 목차
{: .no_toc .text-delta }

1. TOC
   {:toc}

---

## 글을 쓴 배경

Jenkins를 AWS EC2 인스턴스에 설치하는 과정을 기록하기 위해 작성하였습니다.

## 글 요약

AWS EC2 인스턴스에 userdata를 이용하여 Docker로 Jenkins를 Ubuntu OS에 배포하는 방법을 공유합니다.
AWS EC2 인스턴스 생성부터 Docker 이미지를 이용한 배포 프로세스까지 스크립트를 이용해 한번에 설치할 수 있도록 구성하였습니다.

## 시작하기 전

AWS, Docker, Jenkins에 대한 기본적인 이해가 있으신 분들을 위해 작성되었습니다.
AWS EC2 인스턴스 생성 및 설정, Docker에 대한 기본 지식이 필요합니다.

Ubuntu version 22.04 LTS / 사용한 UBUNTU_AMI_ID =ami-09a7535106fbd42d5

사용한 docker image - jenkins/jenkins:jdk17

젠킨슨 버전 - 2.449

사용한 레포지토리 주소 Jenkins-repo

---

## 1. AWS EC2 Ubuntu OS를 awscli를 통해 배포


참고자료 : https://www.jenkins.io/blog/2021/05/20/configure-plugins-with-jcasc/
