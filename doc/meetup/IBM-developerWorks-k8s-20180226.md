# [IBM developerWorks 밋업 : 쿠버네티스, 이젠 정말 써보자!](https://www.onoffmix.com/event/168512)

## 밋업 자료 : https://ibm.biz/201902dw

## 실습환경 설정 : https://ibm.box.com/s/kdskvej8fv9t3ytm8wt2i3jywoksl5f6

 1. IBM Cloud 상의 k8s 클러스터를 생성
 2. 로컬 컴퓨터에서 ibmcloud 커맨드로 클라우드 클러스터에 접속하여, kubectl 로 접근할 환경변수 확인 및 적용
 3. 로컬 컴퓨터에서 kubectl 기본 접근 엔드포인트를 2.로 세팅하여 접근

## k8s 실습내용
 1. https://github.com/IBM/kube101/tree/master/workshop
    - guestbook 이라는 웹서비스를 k8s 클러스터에 배포하는 과정
    - [구조] pod, node, cluster / service, deployment
    - [특징] 클러스터에서 외부에 노출시킬 service가 지정되어야 함
    - 클러스터 컨테이너 포트포워딩을 통한 프런트서버 분산 환경 배포
    - 클러스터 컨테이너 내 프런트서버 + Redis-master + Redis-slave 환경 설정 배포
    - yaml 파일을 통한 service, deployment 구조화 배포
  2. https://github.com/IBM-Developer-Korea/innovate-digital-bank/tree/20190226-meetup/20190226-meetup
    - helm 이라는 툴을 이용하여 service 배포 추상화
    - service 배포 버전관리 용이

## 레퍼런스
 1. 코드 패턴 : https://developer.ibm.com/patterns/
 2. ibmcloud 주요 명령어
```
ibmcloud login
ibmcloud ks cluster-config myinsanecluster00
```
 3. kubectl 주요 명령어
```
kubectl get all
kubectl get all -o wide
kubectl get node
kubectl get pod
kubectl get pod guestbook-8f6d58554-44887 -o yaml
kubectl get service
kubectl get pods -l app=guestboo
kubectl describe pod redis-master-67c878bfb4-mprkq
kubectl create -f .
kubectl delete -f .
kubectl create -f guestbook-deployment.yaml
kubectl delete deployment guestbook-v1
kubectl exec -it redis-master-67c878bfb4-mprkq redis-cli
kubectl edit service guestbook
kubectl set image deployment/guestbook guestbook=ibmcom/guestbook:v2
kubectl rollout undo deployment guestbook
kubectl rollout status deployment guestbook
kubectl scale --replicas=10 deployment guestbook
kubectl expose deployment guestbook --type="NodePort" --port=3000
kubectl run guestbook --image=ibmcom/guestbook:v1
```