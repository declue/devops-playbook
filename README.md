# ansible로 DevOps 환경 만들기


## 사전 준비 사항
- visudo로 ansible을 호출하는 계정은 NOPASSWD가 적용되어야 함
```
{user} ALL=(ALL) NOPASSWD: ALL
```
- 다음의 패키지가 설치되어 있어야 함
```
apt-get install -y ansible
```
- ssh-keygen을 통해 ~/.ssh/id_rsa 파일을 생성해야 함
-  vi /etc/ansible/hosts를 통해 host 추가가 필요
```
[myhosts]
12.34.56.78 ansible_ssh_user=user
```

## 실행 방법
```
ansible-playbook setup_docker.yaml 
ansible-playbook setup_k8s.yaml 
```


## K8S 구성
```
# control-plane
ansible-playbook init_k8s.yaml 

# storage class 설정


# node
ansible-playbook join_k8s.yaml
```

## kubesphere 구성
```

```

# devops-playbook
