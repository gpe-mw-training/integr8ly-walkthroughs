# Example Customisations of an Integreatly cluster


## Running examples

To run an example customisation you need an exiting OpenShift cluster with integreatly installed.

Next you need to get the available inventory file from the manifest secret

```
(mac osx)

oc get secret inventory -n webapp --template '{{index .data "generated_inventory"}}'  | base64 -D > inventory
```

```
(Linux)

oc get secret inventory -n webapp --template '{{index .data "generated_inventory"}}'  | base64 -d > inventory
```

You should also be logged into the cluster as an admin user.

You can then run the example playbook using ```ansible-playbook```

```
ansible-playbook -i inventory playbooks/add_custom_che_stack.yaml
```

## Che custom stack example

[Example playbook](https://github.com/integr8ly/example-customisations/blob/master/installation/playbooks/add_custom_che_stack.yaml)
