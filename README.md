# Ansible role for deploy docker app with docker-compose

## How to use with GitLab CI

```
ansible-playbook --private-key ${SSH_PRIVATE_KEY} \
	-u ${DEPLOY_SERVER_USER} \
        -e "env=${CI_ENVIRONMENT_NAME} \
	app_name=${CI_PROJECT_NAME} \
	project_name=${CI_PROJECT_NAMESPACE} \
	deploy_server_ip=${DEPLOY_SERVER} \
	deploy_server_ssh_port=${DEPLOY_SERVER_SSH_PORT} \
        docker_registry_login=false \
        docker_user=${DOCKER_REGISTRY_USER} \
        docker_password=${DOCKER_REGISTRY_PASSWORD}" \
	-b -i inventory.yml playbook.yml
```
