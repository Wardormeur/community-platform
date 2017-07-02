Github -&gt; CircleCI -&gt; S3 -&gt; CodeDeploy -&gt; Update current instance

AWS initial setup

Apps are linked to a Scaling group and deploy upon scaling-up. 

Configuration of the instance is done \(based on the scaling group configured AMI\) by executing the user-data script, recovering the S3 zen-deploy-prod.sh script. 

Post-deployment, the appspec.yml copy the daemon conf and starts it. The daemon cannot be started before as the Codedeploy triggers after the user-data script.

