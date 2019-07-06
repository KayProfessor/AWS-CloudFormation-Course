# How do you work with multiple files? How do you break your cloudformation templates? 
- Using Nested Stack. Nested Stack is described like other resources ( EC2) but with  ```AWS::CloudFormation::Stack``` type ) 

# How do you say do this in this case and don't do it in another case? Ex Launch DB in prod and don't launch in QA? 
- Using Conditions and sometimes using parameters 

# What does parameter do? 
- Helps users input value to during stack creation. You can pass in / choose instance type , region etc during launch. 

# How do you do something that needs computing power? Or something that's not supported in Cloudformation? 
- Custom Resource let you call a lambda funciton , that does some custom processing and return value to CFT back. Used for things like fetching the latest ami-id for AWS AMI. 

# In how many ways can we deploy cloudformation stacks? 
- Management console 
- CLI 
- SDK 
- API 

# How to validate syntax? 
- With a CLI command. 
```
aws cloudformation validate-template --template-body file://sampletemplate.json
```

# What language do you use ? 
- I like YAML because 
  - syntax is easier to use/ read. 
  - Userdata section is a deal maker for YAML. So easy to implement 
  - Some functions like Sub is easy to implement in YAML 
  - I like being able to use !Ref Name instead of "Ref" : "lName" 

# What's the difference between cloudformation and Terraform ? 
- TF is open source
- Large community contributing to the source code 
- Cloudformation you don't have to manage state file, in terraform you do need to do that. 
- https://www.youtube.com/watch?v=uFaMUS6Z9fI


# How do I easily access DNS names of resource created with terraform 
- Output secton of the template, you specify what to output, like dns name of the load balancer. 

# How to pass passwords and sensative data in Cloudformation? 
- SSM parameter store. You can use '{{resolve:service-name:reference-key}}' tp fetch passwords from Systems manager parameter store. 
- https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/dynamic-references.html



