# Deployment:

## Deploy master to production:
```
ssh -i ~/.ssh/id_rsa ubuntu@ec2-107-21-34-110.compute-1.amazonaws.com
cd /home/deploy/apps/ocp/current
eval `ssh-agent -s` ssh-add
ssh-add ~/.ssh/susan_keys/id_rsa
DEPLOY=chara branch=master bundle exec cap deploy &
DEPLOY=pre_prod branch=master cap deploy &
DEPLOY=chara bundle exec cap stop_daemons
ps aux | grep agent  <-- RUN THIS ON PRODUCTION, not this deployment server
DEPLOY=chara bundle exec cap start_daemons

might need to remove the bundle execs above, or maybe just for staging but something to keep in mind
```

## Deploy ON-1297 to staging:
```
ssh -i ~/.ssh/id_rsa ubuntu@ec2-107-21-34-110.compute-1.amazonaws.com
cd /home/deploy/apps/ocp/current
eval `ssh-agent -s` ssh-add
ssh-add ~/.ssh/susan_keys/id_rsa
DEPLOY=stage branch=staging cap deploy &
DEPLOY=stage cap stop_daemons
ps aux | grep agent  <-- RUN THIS ON STAGING, not this deployment server
DEPLOY=stage cap start_daemons
```

## Deploy one-click-cwc to production
### ssh into the microservice ec2 instance
```
ssh -i ~/.ssh/ocpreboot.pem ubuntu@ec2-35-175-214-35.compute-1.amazonaws.com
```

### Change directory into the project directory
```
cd /home/ubuntu/apps/one-click-cwc
```

### Then there is a shell script run it for deploy
```
./cwc_api_prod_deploy.sh
```


## Deploy one-click-cwc to staging
```
ssh -i ~/.ssh/ocpreboot.pem ubuntu@ec2-35-153-183-73.compute-1.amazonaws.com
cd /home/ubuntu/apps/one-click-cwc
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/susan/id_rsa
git pull origin main
sudo docker-compose -f docker-compose-stage.yml stop
sudo docker-compose -f docker-compose-stage.yml up -d
```
