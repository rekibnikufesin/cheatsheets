###Create EC2 Instance:
`aws ec2 run-instances --image-id ami-XXXXXXXX --instance-type t1.micro --key-name mykeyname --security-group-ids sg-XXXXXXXX --subnet-id subnet-XXXXXXXX`

Windows 2012 R2 base ami: ami-e49a0b8c

###Name/Tag Instance:
`aws ec2 create-tags --resources i-XXXXXXXX --tags Key=Name,Value=MyName`

###Terminate Instance:
`aws ec2 terminate-instances --instance-ids i-XXXXXXXX`

###Common Instance Size
instance|vCPU|Mem
t2.micro|1|1
t2.small|1|2
t2.medium|2|4
m3.medium|1|3.75
m3.large|2|7.5
m3.xlarge|4|15
m3.2xlarge|8|30


