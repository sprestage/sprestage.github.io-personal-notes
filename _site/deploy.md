# Deployment:

## Deploy master to production:
```
ssh -i ~/.ssh/id_rsa ubuntu@ec2-107-21-34-110.compute-1.amazonaws.com
cd /home/deploy/apps/ocp/current
eval `ssh-agent -s` ssh-add
ssh-add ~/.ssh/susan_keys/id_rsa
DEPLOY=chara branch=master bundle exec cap deploy
DEPLOY=pre_prod branch=master cap deploy
DEPLOY=chara bundle exec cap stop_daemons
ps aux | grep agent
DEPLOY=chara bundle exec cap start_daemons
```

## Deploy ON-1297 to staging:
```
ssh -i ~/.ssh/id_rsa ubuntu@ec2-107-21-34-110.compute-1.amazonaws.com
cd /home/deploy/apps/ocp/current
eval `ssh-agent -s` ssh-add
ssh-add ~/.ssh/susan_keys/id_rsa
DEPLOY=stage branch=ON-1297 bundle exec cap deploy
DEPLOY=stage bundle exec cap stop_daemons
ps aux | grep agent
DEPLOY=stage bundle exec cap start_daemons
```
