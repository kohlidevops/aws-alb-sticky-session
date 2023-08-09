# aws-alb-sticky-session

I'm assuming that Application Load balancer is mapped to two different EC2 instances. When I hit the ALB DNS Url,

![image](https://github.com/kohlidevops/aws-alb-sticky-session/assets/100069489/abc68d7a-b7a6-4232-9e19-4e0948e570c4)
![image](https://github.com/kohlidevops/aws-alb-sticky-session/assets/100069489/ec13b319-6bcb-4aad-88d6-f90725ee3538)

**To Configure Stick Sessions**

Navigate to your Target group and select your Target group - Actions - Edit Attributes settings

To enable the Stickiness to work on it

![image](https://github.com/kohlidevops/aws-alb-sticky-session/assets/100069489/fdeb9cf6-f640-4efd-9f87-ff4ac5bca97a)

Stickiness type should be Load balancer generated cookies and stickiness duration between 1 seconds and 7 days.

![image](https://github.com/kohlidevops/aws-alb-sticky-session/assets/100069489/cb571614-ec65-4eaa-940f-3b9f2eab9094)

Then save changes. Once configured the cookies you can inspect the URL with browser. Here I can see the Load balancer traffic serve to once instance instead of multiple instance. I have configured stickiness duration as 1 hour.

If we inspect the browser, the we can see the request cookies, response cookies and its expiration date.

![image](https://github.com/kohlidevops/aws-alb-sticky-session/assets/100069489/789d48fa-84e6-4dcc-ae0d-27d59e92ab6d)

That's it. 

**Cleanup the resources**

Make ensure that resources which used for stickiness should be removed from the account.






