# AWS POLICY EVALUATION LOGIC

## Summary

Notes on working with the policy evaluation logic between IAM, resource, bucket
policies

## Resources

[AWS Logic Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html)

## Explicit Deny

If the code finds even one explicit deny that applies, the code returns a final
decision of Deny
