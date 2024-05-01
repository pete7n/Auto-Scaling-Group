<h1>Create an Auto Scaling group</h1>

<h2>Description</h2>
I created an Auto Scaling group that allowed a set of servers to recover from a failure. It was required that there must be two virtual machines running at all times. To achieve this I created a key pair, and a security group. Next, I created a launch configuration. Finally, I create an Auto Scaling group and tested it.
<br />

<h2>Products and Resources Used</h2>

- <b>AWS</b>
- <b>Key Pairs</b>
- <b>Security Groups</b>
- <b>Launch Templates</b>
- <b>Auto-Scaling Groups</b>
- <b>EC2 Instances</b>

<h2>Project Stages:</h2>

<p align="center">
Created a EC2 key pair to be used to access EC2 instances: <br/>
<img src="https://imgur.com/CERppvQ.png" height="80%" width="80%" alt="ASG"/>
<br />
<br />
Created security group that uses my VPC and configured the rule so that allows HTTP and SHH traffic from anywhere:  <br/>
<img src="https://imgur.com/5QuOEg6.png" height="80%" width="80%" alt="ASG"/>
<br />
<br />
Created a launch template with a Linux AMI, adding my previously created Key Pair for login and the security group: <br/>
<img src="https://imgur.com/hPrmV3H.png" height="80%" width="80%" alt="ASG"/>
<br />
<br />
Created an auto-scaling group, selecting the launch template created earlier and subnets within two availability zones. I also added a tag ‘Name’ so that the instances can be identified and monitored easily:  <br/>
<img src="https://imgur.com/m7NGy1J.png" height="80%" width="80%" alt="ASG"/>
<br />
<br />
The auto-scaling group then launched two instances as specified, so then to test the autoscaling group I terminated one of the instances and the auto-scaling group launched a replacement to maintain the desired number of instances requirede:  <br/>
<img src="https://imgur.com/zFJkUhu.png" height="80%" width="80%" alt="BGG QuickSight"/>
</p>
