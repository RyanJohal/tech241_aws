# Auto Scaling
Auto scaling, in AWS, is a feature that adjusts the number of instances in a fleet based on real-time demand. It automatically adds or removes instances to match the workload, ensuring optimal performance and cost efficiency. It helps handle traffic variations, maintains consistent performance, and optimizes costs by scaling resources as needed.

### Broad steps
1. db VM running
2. create ami for app vm
3. create launch template
4. create autoscaling group
5. create loadbalancer 

# Using autoscaling in aws
1. Create auto scaling group
![Alt text](<Screenshot 2023-07-06 162636.png>)
2. Name auto scaling group
3. Select launch template
 ![Alt text](<Screenshot 2023-07-06 162815.png>)  
4. Select availability zones and subnets
![Alt text](<Screenshot 2023-07-06 163604.png>)
5. Attach new load balancer based on your requirements (I used application and internet facing as this is for a web app)
![Alt text](<Screenshot 2023-07-06 163826.png>)
6. Select routing
7. Turn on health checks
![Alt text](<Screenshot 2023-07-06 163927.png>)
8. Select desired numbers of vms to share load, minimum and maximum.
![Alt text](<Screenshot 2023-07-06 164000.png>)
9. Add tags so new instances have a name.
![Alt text](<Screenshot 2023-07-06 164039.png>)
10. Create your asg
11. To check if it is working go to your load balancer and input dns into your web browser