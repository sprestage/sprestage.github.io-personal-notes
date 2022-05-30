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

24
Host elastic-staging
    HostName ec2-35-153-183-73.compute-1.amazonaws.com
    user ubuntu
    IdentityFile ~/.ssh/ocpreboot.pem

ssh_stage: aliased to ssh -i ~/.ssh/ocpreboot.pem ubuntu@ec2-54-235-144-131.compute-1.amazonaws.com
