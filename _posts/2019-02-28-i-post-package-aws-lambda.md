---
layout: default
title: Package AWS Lambda function
dd: packageawslambda
category: timeline
tags: article
---

- Install/start Docker 
- Install python3
- Install nodejs (npm included)
- Install serverless: npm install -g serverless
- Install virtualenv of python pip install virtualenv

Create Serverless project

```
serverless create   --template aws-python3  --name project-name  --path project-path
```

Active virtualenv at project directory:

```
virtualenv venv --python=python3
# On Windows
.\venv\Script\activate
# On Linux
source venv/bin/activate
```

Install python package and code as usual in python virtual environment

Freeze python package to requirements.txt
`pip freeze > requirements.txt`

Install `serverless-python-requirements` and config the plugin at serverless.yml

``` 
npm install --save serverless-python-requirements
````

```
service: project-name # NOTE: update this with your service name
provider:
  name: aws
  runtime: python3.6
  region: aws-reagon
  role: aws-iam-role-with-the-privilidge-to-create-lambda-function
plugins:
  - serverless-python-requirements
# you can add packaging information here
package:
  exclude:
     - vent/**

functions:
  hello:
    handler: handler.hello
    events:
      - http:
          path: hello
          method: get
          cors: true
          integration: LAMBDA
      - schedule: rate(1 hour)
```

Deploy to AWS:

```
serverless deploy

```

Useful tools:
- serverless logs --function hello #check last log
- serverless invoke -f hello --log #invoke the function
