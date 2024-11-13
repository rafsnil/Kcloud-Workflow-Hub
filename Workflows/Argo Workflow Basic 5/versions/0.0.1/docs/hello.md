INSTRUCTION TO USE THE HELLO TEMPLATE

apiVersion: argoproj.io/v1alpha1
kind: Workflow
metadata:
  generateName: run-template-
spec:
  workflowTemplateRef:
    name: example-template
  arguments:
    parameters:
      - name: message
        value: "Hello from KloverCloud!"
