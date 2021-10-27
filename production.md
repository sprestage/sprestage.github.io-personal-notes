# Production and Staging

## Production
```
ssh_prod

cd /home/deploy/apps/ocp/current/

bundle exec rails c production

rake some_rake_task.rake RAILS_ENV=production

ubuntu@ip-172-30-1-246:/home/deploy/apps/ocp/current$

bundle exec rake import_cicero_australia_shapefiles[record] RAILS_ENV=production
bundle exec rake deactivate_au_recipients_with_no_cicero_code[senate, true, false] RAILS_ENV=production
```

## Staging
```
ssh_stage

cd /home/deploy/apps/ocp/current/

bundle exec rails c production
```

## aliases
```
susanprestage@Susans-MBP canada %  which ssh_prod
ssh_prod: aliased to ssh -i ~/.ssh/id_rsa ubuntu@ec2-184-72-246-33.compute-1.amazonaws.com
susanprestage@Susans-MBP canada % which ssh_stage
ssh_stage: aliased to ssh -i ~/.ssh/id_rsa ubuntu@54.235.144.131
```

## troubleshooting
### missing bundle exec
If you see this error:
```
ubuntu@ip-172-30-1-231:/home/deploy/apps/ocp/current$ rake import_cicero_canada_shapefiles RAILS_ENV=production
rake aborted!
Gem::LoadError: You have already activated rake 10.4.2, but your Gemfile requires rake 13.0.6. Since rake is a default gem, you can either remove your dependency on it or try updating to a newer version of bundler that supports rake as a default gem.
```
it is because you are missing the `bundle exec` before `rake`.

If you see this error:
```
ubuntu@ip-172-30-1-231:/home/deploy/apps/ocp/current$ bundle exec rake import_cicero_canada_shapefiles
...
rake aborted!
LoadError: cannot load such file -- phantomjs/poltergeist
```
it is because you are missing the `RAILS_ENV=production` at the end of a `rake` call.
