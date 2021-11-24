#ansible_dswarm_redis
This is an example Ansible playbook which deploys as many Redis containers as
there are nodes to a Docker Swarm cluster.  It then configures the container 
running on the first node to be the Master and the others to be replicas.

##Note
This playbook assumes that all of the nodes in your Swarm are available to
run containers.  As you are probably well aware, manager nodes should not be
used for this purpose in production.  This playbook was built to simply be a
demonstration.

##Requirements
This playbook uses the community.general and community.docker collections which
are available on Ansible Galaxy.

##Files
###build_redis_cluster.yml
This is the main playbook which launches the roles involved.

###roles/config_swarm/tasks/main.yml
These are the tasks needed to get the Redis containers running and the relevent
info stored

###roles/config_redis/main.yml
These are the tasks needed to configure the Redis containers themselves.
