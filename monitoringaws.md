# How to set up an alarm for monitoring resources in AWS
1. Open instance
2. Select monitoring
3. Click 'view in metrics' on the metric you would like to monitor (I chose CPU Utilisation)
4. Copy the label ID
5. Open the CloudWatch console at https://console.aws.amazon.com/cloudwatch/.
6. In the navigation pane, choose Alarms, All Alarms.
7. Choose Create alarm.
8. Choose Select metric.
9. Paste label ID
10. select average for stats
11. Select the period of time you want it to check the alarm status
In the All metrics tab, choose EC2 metrics.
![Alt text](<Screenshot 2023-07-04 155240.png>)
12. Select the percentage you want to be alerted at.
![Alt text](<Screenshot 2023-07-04 155250.png>)
13. Create new sns topic and enter email to be notified through
![Alt text](<Screenshot 2023-07-04 155410.png>)
14. Launch alarm and wait to be notified!
![Alt text](<MicrosoftTeams-image (4).png>)