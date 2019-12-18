## PoC terraform + AWS Lambda

Terraform is a tool that facilitate infra as code. AWS Lambda is Amazon's serverless computation service. This repo is just a very simple Proof of Concept of how everything works together.

### Steps

1. This will download the necessary plugins that we used in the code, otherwise it won’t be able to run 
`terraform init`

2. This command will take care of doing everything that we defined, it will archive the code, the IAM role and the function itself.
`terraform apply`

3. Try it!
`aws lambda invoke --function-name test_lambda --invocation-type RequestResponse --log-type Tail - | jq '.LogResult' -r | base64 --decode`

4. Clean up
`terraform destroy`
