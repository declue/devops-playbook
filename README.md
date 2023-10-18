# ansible로 DevOps 환경 만들기


## 사전 준비 사항
- .env 파일을 생성해야 한다. 이곳에 sudo 명령어에 사용될 비밀번호가 저장되어 있어야 한다


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
ansible-playbook setup_docker.yaml --extra-vars "ansible_become_pass=${ANSIBLE_BECOME_PASS}"
ansible-playbook setup_k8s.yaml --extra-vars "ansible_become_pass=${ANSIBLE_BECOME_PASS}"
```


## K8S 구성
```
# control-plane
ansible-playbook init_k8s.yaml --extra-vars "ansible_become_pass=${ANSIBLE_BECOME_PASS}"
```
# storage class 설정


# node
```
# work node
ansible-playbook join_k8s.yaml --extra-vars "ansible_become_pass=${ANSIBLE_BECOME_PASS}"
```

## kubesphere 구성
```

```
