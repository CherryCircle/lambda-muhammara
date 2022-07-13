# lambda-muhammara

This repository contains only the pre-built binary for running muhammara in an AWS Lambda function.  This is so you can deploy muhammara to a Lambda function from a Windows machine.  
To do so:
```
npm install muhammara --save
npm install lambda-muhammara --save
copy node_modules/muhammara/binding/muhammara.node node_modules/muhammara/binding/muhammara_backupForMyOS.node
copy node_modules/lambda-muhammara/binding/muhammara.node node_modules/muhammara/binding/muhammara.node
```

And then deploy your lambda function as you would normally.

# Version history:
1. Use Version1 for AWS Lambda Node 14.17.0+
2.5 Updated for Muhamara 2.5 (still using AWS Lambda Node 14.17.0)
