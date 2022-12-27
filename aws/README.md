- [命名規則](#命名規則)
- [参考](#参考)

# 命名規則

| Variable        | Description                                                                       |
| --------------- | --------------------------------------------------------------------------------- |
| {project}       | プロジェクト名                                                                    |
| {env}           | 環境名 [dev, stg, prod]                                                           |
| {n}             | 1 から始まるシーケンシャルな数字                                                  |
| {network-layer} | ネットワーク層 [public, protected, private]                                       |
| {region}        | リージョン                                                                        |
| {role}          | ロール/役割 [migration-server, contents-server, main-db, frontend, backend...etc] |
| {account-id}    | AWS アカウント ID ( サインイン後、右上メニューより確認可 )                        |
| {target}        | ターゲット [alb, clb, ec2, rds, s3, cf, amplify, api, lambda, dynamodb, log]      |

| Kind                 | Example name                                       |
| -------------------- | -------------------------------------------------- |
| VPC                  | {project}-{env}-vpc                                |
| Subnet               | {project}-{env}-subnet-{network-layer}{n}-{region} |
| Route Table          | {project}-{env}-rtb-{network-layer}{n}-{region}    |
| Internet Gateway     | {project}-{env}-igw                                |
| NAT Gateway          | {project}-{env}-natgw-{region}                     |
| ELB                  | {project}-{env}-alb/clb                            |
| Target Group         | {project}-{env}-tg                                 |
| Endpoint             | {project}-{env}-endpoint-{target}                  |
| EC2 Instance         | {project}-{env}-ec2-{role}{n}                      |
| IAM Role             | {project}-{env}-role-{role}                        |
| Security Group       | {project}-{env}-sg-{role}                          |
| RDS                  | {project}-{env}-rds-{role}                         |
| S3 Bucket            | {project}-{env}-s3-{role}-{account-id}             |
| CloudFront           | {project}-{env}-cf-{role}                          |
| Amplify              | {project}-{env}-amplify-{role}                     |
| API Gateway          | {project}-{env}-api-{role}                         |
| Lambda Function      | {project}-{env}-lambda-{role}                      |
| DynamoDB Table       | {project}-{env}-dynamodb-{role}                    |
| CloudWatch Log Group | {project}-{env}-log-{role}                         |
| CloudWatch Metric    | {project}-{env}-metric-{role}                      |
| CloudWatch Alarm     | {project}-{env}-alarm-{role}                       |
| CloudWatch Event     | {project}-{env}-event-{role}                       |

# 参考

- https://gyazo.com/cdcac93572d0a07be9cc0de515c682ab
- https://dev.classmethod.jp/articles/aws-name-rule/
