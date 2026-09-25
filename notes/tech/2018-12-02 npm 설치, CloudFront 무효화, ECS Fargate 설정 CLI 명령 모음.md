# npm 설치, CloudFront 무효화, ECS Fargate 설정 CLI 명령 모음
*작성 2018-12-02 · 수정 2018-12-02*

sudo npm install fsevents  
sudo npm install phantomjs-prebuilt  

aws cloudfront list-distributions --profile <profile>  
aws cloudfront get-distribution --id <DISTRIBUTION_ID> --profile <profile>  
aws cloudfront create-invalidation --distribution-id <DISTRIBUTION_ID> --paths "/*" --profile <profile>  


aws iam --region ap-northeast-1 create-role --role-name ecsTaskExecutionRole --assume-role-policy-document file://task-execution-assume-role.json  

aws iam --region ap-northeast-1 attach-role-policy --role-name ecsTaskExecutionRole --policy-arn arn:aws:iam::aws:policy/service-role/AmazonECSTaskExecutionRolePolicy  

ecs-cli configure --cluster tutorial --region ap-northeast-1 --default-launch-type FARGATE --config-name tutorial  

ecs-cli configure profile default --profile-name <profile>
