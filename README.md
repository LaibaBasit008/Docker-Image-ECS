# Docker-Image-ECS
<p>Set up Node Js application and docker using <a href="https://github.com/LaibaBasit008/Docker-Image-of-Node-Js-App">Docker-Image-of-Node-Js-App</a></p>
<h1>ECR Setup</h1>
<ul>
<li>Create a repository in ECR</li>
<li>Click on View Commands and run them in Ec2 Terminal</li>
<p>This is how the commands look like</p>
<li>aws ecr get-login-password --region  | docker login --username AWS --password-stdin aws_account_id.dkr.ecr.us-east-2.amazonaws.com
</li>
<li>docker build -t ec2-app .</li>
<li>docker tag noderestapi:latest 864227929192.dkr.ecr.us-east-2.amazonaws.com/rest-api:v1</li>
<li>docker push 864227929192.dkr.ecr.us-east-.amazonaws.com/latest
</li>

</ul>
<h1>Create a repository in ECS</h1>

<ul>
<li>
Create a cluster in ECS of networking only type</li>
<li>After creating a cluster. Go to Task Defination</li>
<li>Create a task defination of fargate type</li>
<li>Add a container. Add details from the ECR pushed. Copy Image value from ecr and add it in the image</li>
<li>Go back to task defination and deploy services</li>
<li>While deploying services choose task defination the one created above and deploy</li>
<li>From configuaration of services select security group. Edit inbound rules for all traffic</li>
<li>Determine Public Ip from configuration</li>
<li>Visit IP:3000>
</ul>
