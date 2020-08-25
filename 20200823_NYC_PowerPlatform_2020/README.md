# Video of the session at the event
You can watch the recording of the session at the event following this link: [**Recording of the session**](https://www.youtube.com/watch?v=Uwd_KUxAxKY&list=PLdbM_SIQbJQhyHstSbcEaR93IwFY0phSu&index=8&t=0s)

*Note: The error I got during the session (at 15:40) is due to the fact that the pipeline tried to make a commit at the same time I was making the commit for the creation of the other pipeline.*

# Description of the content of this folder
* **Use_YAML_files_in_Azure_DevOps_to_manage_the_deployment_of_your_solutions.pptx**: slide deck presented at the event
* **Pipelines_YAML**
  * **CI_CD**
    * **manual-publish-export-unpack-commit-solution.yml**: pipeline that need to be trigger manually to make a publish on an environment, export a solution as unmanaged, unpack it and then push it to the repository in the considered branch (3 variables: the commit message, the service connection to use and the solution unique name)
    * **pull-request-quality-check.yml**: multi-stage pipeline showing some verifications you can make on a pull requests regarding a Power Apps solution that will be automatically triggered when a pull request will be created or a new commit made on a branch with an active pull request
    * **build-deploy-solution-to-qa-on-commit-on-main-branch**: mutil-stage pipeline calling the pipeline templates in the "PipelineTemplates" folder that will be automatically triggered on a commit on the main branch (after the merge of a pull request) and that will generate and then push a managed version of the solution from the main branch to the QA environment
    * **build-deploy-solution-to-productionl.yml**: mutil-stage pipeline calling the pipeline templates in the "PipelineTemplates" folder that needs to be trigger manually and that will generate and then push a managed version of the solution from a release branch to the Production environment
  * **PipelineTemplates**: pipeline definitions used as template in some pipeline definitions in the "CI_CD" folder
    * **pack-unmanaged-solution-template.yml**: pipeline template used to pack a solution as unmanaged and publish it as an artifact so it can be used later in the calling pipeline
    * **generate-managed-solution-template.yml**: pipeline template used to generate a managed version of a solution (import unmanaged version of the solution to a build environment, then export it as managed) and publish it as an artifact so it can be used later in the calling pipeline
    * **deploy-managed-solution-template.yml**: pipeline template to deploy a managed version of a solution to a targeted environement specified as string input parameter
  * **Utils**
    * **service-connection-test.yml**: pipeline that will allow you to test a service connection passing its name as input

# Useful resources
* [Power Platform Build Tools Microsoft documentation](https://docs.microsoft.com/en-us/power-platform/alm/devops-build-tools)
* [How to convert Classic UI pipelines to YAML](https://devblogs.microsoft.com/premier-developer/converting-classic-azure-devops-pipelines-to-yaml/)
* [Release Flow: How We Do Branching on the VSTS Team](https://aka.ms/releaseflow)
* [Release Flow page in Microsoft documentation](https://docs.microsoft.com/en-us/azure/devops/learn/devops-at-microsoft/release-flow)
* ["Approvals in environments with multi-stage YAML pipelines" by Sam Smith](https://samlearnsazure.blog/2020/02/05/approvals-in-environments/)
* [How to extract the branch full name from the "Build.SourceBranch" predefined variable](https://github.com/microsoft/azure-pipelines-agent/issues/838#issuecomment-641201222)
* ["Azure DevOps YAML pipeline : Template = task group" by Kenichiro Nakamura](https://dev.to/kenakamu/azure-devops-yaml-pipeline-template-task-group-56bb)
