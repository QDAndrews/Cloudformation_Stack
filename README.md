# Cloudformation_Stack

Original code is here: 

#### Step 1 #######

Resources:
  RobotAppServer:
    Type: 'AWS::EC2::Instance'
    Properties:
      InstanceType: t2.micro
      ImageId: ami-087c17d1fe0178315

###################

#### Step 2 #######

  RobotAppSecurityGroup:
    Type: 'AWS::EC2::SecurityGroup'
    Properties:
      GroupDescription: Enable SSH access via port 22
      SecurityGroupIngress:
      - IpProtocol: tcp
        FromPort: '22'
        ToPort: '22'
        CidrIp: 0.0.0.0/0

###################

#### Step 3 #######

      SecurityGroups:
      - !Ref RobotAppSecurityGroup

###################

#### Step 4 #######

  RobotS3Bucket:
    Type: 'AWS::S3::Bucket'
    DeletionPolicy: Delete

###################

Object is to change to T2 small and create new stack (change the name of the stack and save as new stack) 

CloudFormation- Speed up cloud provisioning with infrastructure as code
Stacks wiki: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacks.html
