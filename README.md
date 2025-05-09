# lab-step-fns-basics
AWS Serverless

Building a proof of concept using AWS Serverless Application Model (AWS SAM). Two state machines:
The first is a simple "Hello World" workflow with a wait state that delays execution and a pass state that returns "Hello World." 
The second is a calculator workflow that takes input numbers, and performs simple mathematical calculations using a Lambda function. Demonstrate Task, InputPath, ResultPath, and OutputPath capabilities in Step Functions. 
Define the workflows in an AWS SAM template, deployed them using AWS SAM CLI, and tested their execution. 

Background:

The Calculator Step Functions Workflow demonstrates how data is filtered and transformed as it flows through the state machine using InputPath, ResultPath, and OutputPath. These properties define how input is processed, how results are stored, and how the final output is structured.

InputPath is used to extract only the relevant portion of the input JSON before passing it to the Lambda function. In this workflow, it ensures that only the necessary input data, such as operands and the operation type (stored under lambda property of input JSON), is sent to the Lambda function for processing. This prevents unnecessary data from being passed to the function, making execution more efficient.

ResultPath determines where the Lambda function’s output is stored within the execution context of the Step Function. Instead of replacing the entire input, the function’s result is stored within a specific field inside the state’s output (lambda.lambdaResult in this case), allowing the workflow to retain both the original input and the computed result.

OutputPath filters the final state output, ensuring that only relevant data is returned at the end of execution. It removes unnecessary attributes from the final output while keeping both the input and the computed result structured in a meaningful way. This ensures that downstream systems or the next state in the workflow receive clean, well-structured data.

Together, these path selectors optimize data handling in Step Functions by controlling what gets passed, stored, and returned, making workflows more efficient and reducing unnecessary processing.


![image](https://github.com/user-attachments/assets/3ecb52de-e001-41e7-af00-9e9c3524932e)
