# Deployment:

## Deploy master to production:
```
ssh -i ~/.ssh/id_rsa ubuntu@ec2-107-21-34-110.compute-1.amazonaws.com
cd /home/deploy/apps/ocp/current
eval `ssh-agent -s` ssh-add
ssh-add ~/.ssh/susan_keys/id_rsa
DEPLOY=chara branch=master cap deploy &
DEPLOY=pre_prod branch=master cap deploy &
DEPLOY=chara cap stop_daemons
ps aux | grep agent  <-- RUN THIS ON PRODUCTION, not this deployment server
DEPLOY=chara cap start_daemons


ssh -i ~/.ssh/id_rsa ubuntu@ec2-107-21-34-110.compute-1.amazonaws.com
cd /home/deploy/apps/ocp/current
eval `ssh-agent -s` ssh-add
ssh-add ~/.ssh/susan_keys/id_rsa

DEPLOY=chara branch=master cap deploy &

DEPLOY=chara cap stop_consumers
DEPLOY=chara cap start_consumers
```


## Deploy master to staging:
```
ssh -i ~/.ssh/id_rsa ubuntu@ec2-107-21-34-110.compute-1.amazonaws.com
cd /home/deploy/apps/ocp/current
eval `ssh-agent -s` ssh-add
ssh-add ~/.ssh/susan_keys/id_rsa

DEPLOY=stage branch=staging cap deploy &

DEPLOY=stage branch=staging cap stop_consumers
DEPLOY=stage branch=staging cap start_consumers
```


## Deploy one-click-cwc to production
### ssh into the microservice ec2 instance
```
ssh -i ~/.ssh/ocpreboot.pem ubuntu@ec2-34-225-246-219.compute-1.amazonaws.com
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
