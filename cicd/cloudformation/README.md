# SSO Sync Pipelines

There are a number of cloudformation templates depending on what your need to deploy. For most developers 
You need 
* secrets.yaml - creates the secrets for storing the credentials for your test GSuite and IAM Identity Center instances
* developer.yaml - creates the pipeline to build and test prior to raising a pull request.

The other option is for the production build, deploy and test environment, which requires, two AWS accounts *production* and *staging*:
* First setup to *staging* account
  * secrets.yaml - creates the secrets for storing the credentials for your test GSuite and IAM Identity Center instances
  * staging.yaml - creates the pipeline to deploy and test prior to raising a pull request.
Make a note of the output values

* Now setup your *production* account
  * Manually create your code star connection
  * production.yaml - creates the pipeline to build, trigger the test pipeline in staging and where appropriate publish the app


