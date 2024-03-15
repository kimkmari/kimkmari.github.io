---
layout: default
title: Jenkins Configuration as Code 를 이용하여 Jenkins 설치하기
nav_order: 2
permalink: docs/02_Tech/CICD/Jenkins/Installation
parent: CICD
grand_parent: Tech
---

# Jenkins Configuration as Code 플러그인을 사용하여 사용자 정의 구성이 적용된 Jenkins Docker 서비스 배포하기
{: .no_toc }

## 목차
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## 글을 쓴 배경

단순한 Jenkins 배포가 아닌 유저 프로비저닝 등 다양한 젠킨슨 설정을 자동으로 구성할 필요성을 느끼게 되었습니다.

## 글 요약

1. 역할 기반 설정과 관리자 사용자의 자격 증명을 포함하는 jenkins.yml 파일을 생성합니다.
2. 환경 변수 CASC_JENKINS_CONFIG를 설정하여 첫 번째 단계에서 생성한 jenkins.yml 파일을 배치할 위치를 지정합니다.
3. jenkins.yml 파일을 CASC_JENKINS_CONFIG의 위치에 바인드 마운트합니다.

Jenkins 설정을 YAML 파일로 정의함으로써 사용자 지정 젠킨슨 구성을 자동화 합니다.

- **Jenkins Configuration as Code**:
- **Role-based-Authorization Strategy**:

## 시작하기 전

Jenkins와 AWS에 대한 기본적인 사용 경험을 가진 DevOps 엔지니어를 대상으로 합니다.
Jenkins에 대한 기본적인 이해가 필요합니다.

사용한 레포지토리 주소 Jenkins-repo

## 구현 프로세스



## EC2 인스턴스에 사용자 정의 구성내용을 포한한 Jenkins 인스턴스 배포

awscli를 활용한 ec2 배포 부분은 앞선 기본 배포 방식과 동일합니다.
본 내용에서는 최초 젠킨슨 이미지를 배포할 때 유저 프로비저닝 등 다양한 환경구성을 함께 적용하여 배포하는 방식을 공유합니다.

### awscli를 활용한 EC2 배포
```shell
aws ec2 run-instances \
  --image-id ${UBUNTU_AMI_ID} \
  --count 1 \
  --instance-type t3.large \
  --key-name ${KEY_NAME} \
  --iam-instance-profile Name=${INSTANCE_PROFILE_ROLE} \
  --subnet-id ${SUBNET_ID} \
  --security-group-ids ${JENKINS_SG} \
  --tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=jenkins-aws-cli-generate}]' \
  --block-device-mappings 'DeviceName=/dev/sda1,Ebs={VolumeSize=100}' \
  --user-data file://userdata.txt
``` 

### userdata를 이용한 Jenkins 자동배포





