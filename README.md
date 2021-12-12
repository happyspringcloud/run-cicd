# run-cicd: CI/CD tool using linux shells

It is CI/CD tool to deploy workloads on kubernetes.   
This tool have shells, yaml template files, Dockerfiles.      
   
You must follow rules to use this tool.  
please, refer below link.    
[run-cicd: Linux shell로 만든 가벼운 CI/CD tool](https://happycloud-lee.tistory.com/195)

## How to install
- Login VM server  
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
- clone your project(아래 예는 webhook) to deploy and Move to project root 
```
$ cd ~/work
$ git clone https://github.com/sc-hklee/webhook.git
$ cd webhook/
```
- Check you've created image pull secret
You MUST create image pull secret for image registry to pull container image  
For example, If your image registry is 'myharbor.io', Make secret as followed.   
``` 
kubectl create secret docker-registry myharbor.io --docker-server=myharbor.io --docker-username={username} --docker-password={password} -n {namespace}    
```
   
- run cicd
```
$ run-cicd
```
TIP) You can also run it using parameters   
If you don't use Spring Cloud Config server, you must skip last parameter.   
```
run-cicd {id for image registry} {password for image registry} . {profile} . {language} [{config server ingress host}]
ex1) run-cicd hklee passw0rd . dev . java 
ex2) run-cicd hklee passw0rd . dev . java config.169.56.70.nip.io
```

## for Mac user
install jq-mac
```
❯ cd ~/run-cicd/cmd
❯ ll
...
-rwxr-xr-x  1 happycloudpak  staff   257K  1 15 13:18 jq-mac
...
❯ cp jq-mac /usr/local/bin/jq
❯ install /usr/local/bin/jq ~/run-cicd/cmd/jq
```


