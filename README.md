# Hosting a Dynamic Website or Web App on AWS

In this project I will use AWS services to host a *_Dynamic Website or Web App_*. The following diagram shows the services used for this project.

![Diagram]()

# 1. Build a 3 Tier AWS Network VPC

I start off by logging in to the AWS console and selecting the desired region. Next I will go to the VPC console click on VPCs.

![Click on VPCs]()

Next click on create VPC. I will use the referance diagram to fill out the information needed and create VPC. 

![Name and Create]()

Next on the left I will filter by the VPC that I jsut created then click actions and select *_Edit VPC settings_* andf enable DNS hostnames.

![Enable and save]()


Next I will create an internet gateway by clicking on internet gateway on the left hand side and then click on *_Create internet gateway_*. 

![Name IG and create]()

Next I will attach the *_Internet Gateway_* to the *_VPC_* by clicking on the __'Attach to a VPC'__ button at the top of the page 

![Attach to a VPC]()

Next I will click on the search box and it will only show the VPC that does not have an __Internet Gateway__ attached to it since we are only able to add one internet gateway a VPC. I will select the VPC and click *_Attach internet gateway.   

![Select VPC and create]()


Next I will create the *_Public Subnets_* in the 1st and 2nd *_Availability Zones_*. I'll start by clicking on the *_Subnets_* link on the left. I am still filtering by the VPC so no other VPCs should show, now I will click on *_Create Subnet_*. From the drop down box I will select the __VPC__. Then i will scroll down and fill out the information using the diagram as referance. 

![AZ1 us-east-1a]()

Next I will create the 2nd *_Public Subnet_*  by doing the same as the previous subnet and use the information for the 2nd *_Availability Zone_*. 

![AZ2 us-east-1b]()


Next I will enable the auto assing *_IP Settings_* for the 2 __Public Subnets__ this will auto assing an IPv4 address to any __EC2__ instance that is lanche in the __Public Subnets__. To auto assing I will select a subnet, click __Actions__ and select *_Edit subnet settings_*.

![edit subnet settings]()

Next I will *_Enable auto-assing public IPv4 address_* and do the same for the other __Public Subnet__.

![enable auto assing and save]()
 

Next I will create the *_Route Table_*, first I will click on *_Route Table_* on the left, then click *_Create Route Table_*. Next I will name the *_Rout Table_* and in the drop down I will select teh __Dev VPC__ and then click on *_Create Route Table_*.

![Create Route Table]()

Next I will add a *_Public Route_* to the __Route Table__. The *_Public Route_* will allow the route table to route traffic to the internet. First select the *_Routes_* tab and click *_Edit Routes_*.

![Edit Routes]()

Next I will click on *_Add route_* and fill out the information with the following.

![add route and save]()

When created the route will show under the routes tab.Next i will be associating the __Route Table__ to the __Public Subnets__. By clicking on the *_Subnet Associations_* tab, then on the *_Edit Subnet Associations_*. Next it will show the __Public Subnets__, I will check both of the boxes and then click *_Save Associations_*.

![Save Association]()

Next to finish creating the VPCs I will create the *_Private Subnets_*. On the left I will click on __Subnets__, then __Create Subnets__. Next I will fill out the information as shonw in the referance diagram and repeat for the other 3 *_Private Subnets_* and at the end i can verify what I created by clearing the filter and filtering by the __VPC__.

![all Subnets]()

