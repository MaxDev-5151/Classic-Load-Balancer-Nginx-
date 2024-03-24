# Implementation of Classic Load Balancer with two EC2 Instances(Using Apache2 Web-server)

**1. Create two EC2 instances with same config**
![Image](./images/Apache2/1.png)

**2. ssh 1st EC2 Instance and install Apache2 server**
- ssh -i "max123.pem" ubuntu2-34-229-106-17.compute-1-1.amazonaws.com
- `sudo -i`
- `apt-get update`
- `apt-get install apache2`

![Image](./images/Apache2/2.png)
![Image](./images/Apache2/3.png)
- For Checking Active status of server: `service nginx status`
- For Interact with server type: `curl localhost`
- Then go to default location of server type: `cd /var/www/html`
- For file check type: `ls`
- For Checking content of file type: `cat index.html`

![Image](./images/Apache2/4.png)
- For print "Welcome Machine 1..!" on page type: `echo "Hello Machine 1..!">index.html`

![Image](./images/Apache2/5.png)

**3. Go to chrome put 1st instance public ip, then we can see "Welcome Machine 1..!" on web page**

![Image](./images/Apache2/6.png)

**4. Then follow same process for instance 2, After successfully done process then open public ip of 2nd instance on chrome we can see "Hello Machine 2...!" is display on web page**

![Image](./images/Apache2/7.png)

**5. Then After go to Load Balancer page and click on 'Create Load Balancer'**
![Image](./images/2.png)

**6. Open Classic Load Balancer and then click on 'Create' for creating Classic Load Balancer**

![Image](./images/3.png)

**7. Enter meaningful Name for our Load Balancer**

![Image](./images/3a.png)

**8. Then in Network mapping section select our instance Availability Zone**

![Image](./images/6.png)

**9. Default Security group, Listeners and routing and Health check**

![Image](./images/4a.png)

**10. Then Instances section click on 'Add Instances' button to add our both instances.**

![Image](./images/5.png)

**11. default Attributes and Review the Summary and click on 'Create Load Balancer'**

![Image](./images/7.png)

**12. After successfully add load balancer then click on view load balancer**

![Image](./images/8.png)

**13. In Load Balancer page go to Security page and click on Security group Id**

![Image](./images/8a.png)

**14. Click on 'Edit inbound rules' button**

![Image](./images/10.png)

**15. Then click on Add rule and select Type: HTTP and Source: Anywhere**

![Image](./images/11.png)

**16. After successfully add rule then review the details**

![Image](./images/12.png)

**17. Then go to Load Balancer page and copy DNS Name**

![Image](./images/13.png)

**18. Go to Browser and open DNS name and For checking refresh page then we can see changes like 'Hello Machine 1..!' to 'Hello Machine 2..!' then we can say load balancer working fine!**

![Image](./images/13a.png)
