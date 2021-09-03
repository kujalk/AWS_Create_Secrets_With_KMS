- Resources created by this CloudFormation template,
 1] KMS Key
 2] AWS Secret Manager Secret
 3] Required IAM policies to the users
 
- This CloudFormation Template take 4 parameters
 1] ProjectName - Name of this project. This will be used add a prefix in Tags of the resources created
 2] SecretNameSpace - Name of the secret. Eg -> /prod/database/sql01
 3] AccessPolicy - Read/Write//ReadWrite policy to access the created secret.
 4] UsersList - IAM users separated by "," Eg -> Jana,John,Peter 

 - This Cloudformation by default create a random string and store it in the created Secret

CLI command ->
aws cloudformation create-stack --stack-name Secret-KMS-Stack --template-body file://SecretManager_KMS_Policies.yaml --parameters ParameterKey=ProjectName,ParameterValue=TestKMS 
ParameterKey=SecretNameSpace,ParameterValue=/prod/database/sql01 ParameterKey=AccessPolicy,ParameterValue=WriteOnly ParameterKey=UsersList,ParameterValue="user1\,user2" --capabilities CAPABILITY_NAMED_IAM

Developer - K.Janarthanan