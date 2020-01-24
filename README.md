# Overview
Stack for [showwin/ISHOCON2](https://github.com/showwin/ISHOCON2)

# Commands

```
aws cloudformation validate-template\
  --template-body file://`pwd`/template.yml

aws cloudformation create-stack \
  --stack-name ishocon2-resources \
  --template-body file://`pwd`/template.yml \
  --parameters file://`pwd`/parameters/production.json

aws cloudformation create-change-set \
  --stack-name  ishocon2-resources \
  --change-set-name remove-benchmarker-eip \
  --template-body file://`pwd`/template.yml \
  --parameters file://`pwd`/parameters/production.json

aws cloudformation list-change-sets \
  --stack-name ishocon2-resources

aws cloudformation describe-change-set \
  --stack-name ishocon2-resources \
  --change-set-name remove-benchmarker-eip

aws cloudformation execute-change-set \
  --stack-name ishocon2-resources \
  --change-set-name remove-benchmarker-eip

aws cloudformation delete-change-set \
  --stack-name ishocon2-resources \
  --change-set-name remove-benchmarker-eip

aws cloudformation update-stack \
  --stack-name ishocon2-resources \
  --template-body file://`pwd`/template.yml \
  --parameters file://`pwd`/parameters/production.json

aws cloudformation delete-stack \
  --stack-name ishocon2-resources
```

# References

- [AWS リソースおよびプロパティタイプのリファレンス](https://docs.aws.amazon.com/ja_jp/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
- [Fn::GetAtt: 他のリソースからの参照](https://docs.aws.amazon.com/ja_jp/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-getatt.html)