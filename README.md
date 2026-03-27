# ECR-ECS Task


### Live Deployement Link:

- [http://test-lb-1505379945.us-east-1.elb.amazonaws.com/](http://test-lb-1505379945.us-east-1.elb.amazonaws.com/)
## Steps

- [1. Create an Amazon ECR repository](#step-1)
- [2. Authenticate Docker with ECR and push the image](#step-2)
- [3. Create VPC networking](#step-3)
- [4. Create ECS cluster](#step-4)
- [5. Create ECS task definition](#step-5)
- [6. Create security groups](#step-6)
- [7. Create ELB and target group](#step-7)
- [8. Create ECS service and attach it to the load balancer](#step-8)
- [9. Test screenshots](#step-9)

---

### <a id="step-1"></a>2. Create an Amazon ECR Repository
![AWS ECR Repository](image.png)

### <a id="step-2"></a>3. Authenticate Docker with ECR and Push the Image

- Steps to Build and Push Image:

  ```bash
  aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 468629753336.dkr.ecr.us-east-1.amazonaws.com
  docker build -t flask-app .
  docker tag flask-app:latest 468629753336.dkr.ecr.us-east-1.amazonaws.com/flask-app:latest
  docker push 468629753336.dkr.ecr.us-east-1.amazonaws.com/flask-app:latest
  ```

### <a id="step-3"></a>4. Create VPC Networking

- Create VPC (Virtual Private Cloud)
  ![alt text](image-1.png)

### <a id="step-4"></a>5. Create ECS Cluster

- ECS Cluster
  ![alt text](image-2.png)

### <a id="step-5"></a>6. Create ECS Task Definition

- Container Configuration
  ![alt text](image-3.png)
- Container Network
  ![alt text](image-4.png)

### <a id="step-6"></a>7. Create Security Groups

- Load Balancer SG
  ![alt text](image-5.png)

- ECS Service SG
  ![alt text](image-6.png)

### <a id="step-7"></a>8. Create ELB and Target Group

- Load Balancer
  ![alt text](image-7.png)
- Target Group
  ![alt text](image-8.png)

### <a id="step-8"></a>9. Create ECS Service and Attach It to the Load Balancer

- ECS Service
  ![alt text](image-9.png)
- ECS Service Tasks
  ![alt text](image-10.png)

### <a id="step-9"></a>10. Verify Deployment with Test Screenshots

- Test 1
  ![alt text](image-11.png)
- Test 2
  ![alt text](image-12.png)
- Test 3
  ![alt text](image-13.png)