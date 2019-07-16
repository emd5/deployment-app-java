# Continuous Delivery/Integration

Implement and document a basic CI/CD Pipeline

# Authors

Yuan Gao, Ed Abrahamsen, Liz Mahoney, Jen Shin

## Deployed Link

http://deploymentjavaapp-env.aigdmphqtg.us-west-2.elasticbeanstalk.com/


## Getting Started

FORK the repository for the application assigned.

Implement a CI/CD pipeline with the following basic steps:

- Source, pulled from the master of your repository every time that branch is updated
- Deploy that source to an appropriate destination ec2, ecs, ebs, etc.
- DOCUMENT the process for “future you” (or, more likely, another team)

Create a new repository for your documentation, called doc-pipeline-app (i.e. doc-pipeline-java)
- Create a README.md
- Include step by step instructions
- Screenshots or supplementary drawings where appropriate
- Troubleshooting tips
- Identify potential roadblocks or trouble spots
	- [x]	Pipeline timeout on us when we were creating an EBS instance so we had to redo the form.
- Provide a means of proving that the pipeline works
- Provide a means of proving repeatability\


## Steps 

***IN THE PROJECT -> application.properties -> `server.port=5000`

1. Create a AWS pipeline called `deployment-app-java`
2. Select `service role	`, 
3. Role name is `deployment-app-java`
4. Enter `next`
5. Source select `github` 
6. Then allow permission for pipeline to use github
7. Select the repo `deployment-app-java`
8. Branch: `master`
9. Change detection options: `github webhooks`
10. Enter `next`
11. Skip build stage
12. Add deploy stage select deploy provider: `AWS Elastic Beanstalk`
13. Go to EBS
14. Create a new instance named `deployment-app-java`
15. Enter description
16. Enter `Create`
17. Select environment tier
18. Click `web server environment`
19. Next to Application code select: `Sample Application`
20. Go back to Pipeline and select the EBS enivronment that you created.
21. Review your settings make sure everything looks good.
22. Select `Create pipeline`
23. The page should redirect to `deployment-app-java` console, this is where the magic happens, status should be green
24. **UPLOAD bootjar file to EC2 instance


## Resources
Java repo - https://github.com/codefellows/deployment-app-java
AWS - https://aws.amazon.com/codepipeline/