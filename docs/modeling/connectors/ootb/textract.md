---
Title: Textract connector
---

# Textract connector
The Textract connector uses the [Amazon Textract service](https://aws.amazon.com/textract/) to extract text and metadata from `JPEG` and `PNG` files that are less than 5mb in size.

The `implementation` value of the Textract connector in a service task would be similar to the following:

```xml
<bpmn2:serviceTask id="ServiceTask_6thy7kl" implementation="textractConnector.EXTRACT" />
```

## Amazon Web Services (AWS) configuration
The Amazon Textract APIs called are the [Detect Document Text API](https://docs.aws.amazon.com/textract/latest/dg/API_DetectDocumentText.html) which joins all `LINE` block objects with a line separator between them and the [Analyze Document API](https://docs.aws.amazon.com/textract/latest/dg/API_AnalyzeDocument.html) with `FORM` and `TABLES` analysis. 

The Textract connector requires an AWS account to access Amazon features. It also requires an [Identity and Access Management (IAM)](https://aws.amazon.com/iam/) user to have the `textract:DetectDocumentText` and `textract:AnalyzeDocument` permissions. 

## Input parameters
The following are the parameters that can be passed to the Textract connector as input parameters using the `EXTRACT` action:

| Parameter | Description | Type | Required? |
| --------- | ----------- | ---- | --------- | 
| `nodeId` | The node ID of the image to use from Alfresco Content Services | String | `*` |
| `uri` | The URI of the image to use | String | `*` |
| `files` | A [file](../../files.md) uploaded in a process and set as a process variable or uploaded as part of a form or another connector | File | `*` |
| `outputFormat` | Sets the output format to `JSON` or `txt`. The default is `JSON` | String | No |
| `confidenceLevel` | The minimum confidence level to use for a label. The default is 0.75 | String | No |
| `timeout` | The timeout period for calling the Textract service in milliseconds | Integer | No | 

`*` Only one of these parameters is required.

## Output parameters
The following are the parameters that are returned to the process by the Textract connector as output parameters using the `EXTRACT` action:

| Parameter | Description | Type |
| --------  | ----------- | ---- |
| `textract.error` |  A list of errors if any are caught by the connector | String |
| `awsResult` | The result of the image analysis. The format is defined by the [input parameter](#input-parameters) `outputFormat` | JSON |

## Configuration parameters
Values for configuration parameters that are specific to a connector instance can be set in the modeling application or during application deployment.

The following are the configuration parameters that need to be set for the Textract connector: 

| Parameter | Description | Required? |
| --------- | ----------- | --------- |
| `AWS_ACCESS_KEY_ID` | The access key to be used to authenticate against AWS | Yes |
| `AWS_SECRET_KEY` | The secret key to be used to authenticate against AWS | Yes |
| `AWS_REGION` | The region of AWS to use the Textract service in | Yes | 
| `AWS_S3_BUCKET` | The name of the S3 bucket to use | Yes |
| `ALFRESCO_CONTENT_REPO_BASE_URL` | The base URL of the Content Services deployment |
