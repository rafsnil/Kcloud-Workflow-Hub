# submit-workflow

## Summary
A wrapper on top of argo cli submit operation.

The template provides the easy ability to submit new workflows without waiting for their result.

This is useful in case you want to trigger a new workflowTemplate without having to wait for its execution or have it affect on your own final satus

## Inputs/Outputs

### Inputs
* TEMPLATE_NAME (required) - The template name
* ENTRYPOINT (required) - The specific template to use as an entrypoint

### Outputs
Child workflow definition (json format) in `outputs.parameters.codefresh-io-child-workflow-def`

## Examples

### Submit a workflow 
```
name: report-commits-status-failure
when: '{{workflow.status}} =~ "Failed|Error"'
templateRef:
  name: argo-hub.gitlab.0.0.1
  template: commit-status
arguments:
  parameters:
    - name: BUILD_BASE_URL
      value: http://your.argo-workflow
    - name: REPO_OWNER
      value: codefresh-io
    - name: REPO_NAME
      value: argo-hub
    - name: REVISION
      value: sha
    - name: STATE
      value: failure
    - name: CONTEXT
      value: name
    - name: DESCRIPTION
      value: Workflow failed
    - name: GITLAB_TOKEN_SECRET
      value: gitlab-token
```
