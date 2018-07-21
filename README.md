Deploy (Create/Update) a CloudFormation Stack with Ansible
---

A simple example of how Ansible can be used to handle CloudFormation stack deployments. Ansible will automatically handle creation or update of the stack as required (which is particularly useful for CI/CD).

The included vars file and CloudFormation template shows how stack parameters (for multiple environments) can be managed in source control. Ansible is also used to lookup Parameter Store values and implement simple password rotation.

Any rotating_secrets in the vars file will be created and rotated automatically on each deployment.

To run the playbook, passing in a vars file and chosen environment:

```
AWS_PROFILE=<profile> ansible-playbook ansible-deploy-stack.yaml --extra-vars"vars_file=database-template-vars.yaml env=dev"
```

