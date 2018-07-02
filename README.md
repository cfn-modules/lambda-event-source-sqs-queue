# cfn-modules: AWS Lambda event source: SQS queue

SQS queue event source for AWS Lambda function.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/lambda-event-source-sqs-queue
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Function:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        LambdaModule: !GetAtt 'Lambda.Outputs.StackName' # required
        QueueModule: !GetAtt 'Queue.Outputs.StackName' # required
        BatchSize: 10 # optional
      TemplateURL: './node_modules/@cfn-modules/lambda-event-source-sqs-queue/module.yml'
```

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>LambdaModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/lambda-function">lambda-function module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>QueueModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/sqs-queue">sqs-queue module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>BatchSize</td>
      <td>The largest number of messages that Lambda retrieves from your queue at once.</td>
      <td>10</td>
      <td>no</td>
      <td>[1-10000]</td>
    </tr>
  </tbody>
</table>
