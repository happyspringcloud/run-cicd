# run-cicd: CI/CD tool using linux shells

It is CI/CD tool to deploy workloads on kubernetes.   
This tool have shells, yaml template files, Dockerfiles.      
   
You must follow rules to use this tool.  
please, refer below link.    
[run-cicd: Linux shell로 만든 가벼운 CI/CD tool](https://happycloud-lee.tistory.com/195)

## How to install
- Login centos server  
- switch os user 
- clone tool
```
$ git clone https://github.com/happyspringcloud/run-cicd.git 
```
- make symbolic link
```
$ sudo ln -s ~/run-cicd/cmd/run-cicd /usr/local/bin/run-cicd
```

## How to run
- Move to working directory
- clone your project to deploy and Move to project root 
```
$ cd ~/work
$ git clone https://github.com/sc-hklee/webhook.git
$ cd webhook/
```
- run cicd
```
$ run-cicd
```
TIP) You can also run it using parameters
```
run-cicd {id for image registry} {password for image registry} . {profile} . {language} {config server ingress name} 
ex) run-cicd hklee passw0rd . dev . java config 
```

## for Mac user
Replace jq with jq-mac
```
$ cd ~/run-cicd/cmd
$ rm jq
$ cp jq-mac jq
```


