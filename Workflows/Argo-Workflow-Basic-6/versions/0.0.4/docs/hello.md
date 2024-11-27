INSTRUCTION TO USE THE HELLO TEMPLATE

```
name: submit
templateRef:
  name: argo-hub.argo-workflows.0.0.4
  template: submit-workflow
arguments:
  parameters:
    - name: TEMPLATE_NAME_1
      value: 'argo-hub.argo-workflows-utils.0.0.1'
    - name: ENTRYPOINT_1
      value: 'echo'
```