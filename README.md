# Hands-On Cloud Security Labs (AWS, Azure, GCP, Kubernetes)

The quickest way to learn cloud security is to break things in a real cloud environment and then work out how a defender would have caught you. This list collects the hands-on labs, vulnerable-by-design environments and challenges we point people to when they ask where to start, from free hosted labs that need nothing more than a browser to Terraform environments you deploy into your own account.

> **Key Takeaway:** Cloud attack paths are usually identity attack paths. A leaked access key, an over-permissioned role or a managed identity with too much reach does more damage than any exposed port, so the labs worth your time are the ones that make you enumerate permissions, escalate through IAM and pivot between services, and then find that same activity in CloudTrail or the activity logs.

Maintained by [Pwned Labs](https://pwnedlabs.io). Our own labs are listed alongside the community projects we rate, and marked so you know which is which. Pull requests are welcome.

## Hosted labs: just plug and pwn

These run in environments the provider manages, so there is no cloud bill to worry about and nothing runs against an account you care about.

| Lab platform | Clouds | Free tier | What you get |
|---|---|---|---|
| [Pwned Labs](https://pwnedlabs.io/explore) (ours) | AWS, Azure and Microsoft 365, GCP and Google Workspace, Kubernetes, OCI | Over 30 free scenarios with a free account | 90 scenarios in live cloud environments, 15 of them defensive (CloudTrail and Athena investigations, GuardDuty, Security Hub, Splunk). Everything runs in the browser and you do not need your own cloud account. |
| [Cybr hands-on labs](https://cybr.com/hands-on-labs) | AWS | 20+ free labs with a free account | Focused labs on AWS CLI basics, IAM, S3 and Secrets Manager enumeration, and IAM privilege escalation. A good place to build muscle memory. |
| [Hack The Box BlackSky](https://www.hackthebox.com/business/professional-labs/cloud-labs-blacksky) | AWS, Azure, GCP | Business offering | A professional lab per cloud, aimed at teams. |

## Vulnerable-by-design environments you deploy

These are excellent for repeating an attack path from scratch once you understand it. Deploy them into a dedicated account that has nothing else in it, set a budget alert first, and tear everything down when you are done, because some of them are deliberately exposed to the internet.

### AWS

- [CloudGoat](https://github.com/RhinoSecurityLabs/cloudgoat) from Rhino Security Labs. The classic scenario-based AWS environment, with each scenario built around a realistic attack path.
- [IAM Vulnerable](https://github.com/BishopFox/iam-vulnerable) from Bishop Fox. Seth Art's playground of IAM privilege escalation paths, and a great way to understand why `iam:PassRole` keeps turning up in real reports.
- [CloudFoxable](https://github.com/BishopFox/cloudfoxable) from Bishop Fox. A CTF-style environment designed to be explored with CloudFox.
- [AWSGoat](https://github.com/ine-labs/AWSGoat) from INE. A deliberately vulnerable application stack running on AWS.
- [sadcloud](https://github.com/nccgroup/sadcloud) from NCC Group. Stands up, and tears down, insecure AWS configurations so you can see what your tooling flags.

### Azure

- [AzureGoat](https://github.com/ine-labs/AzureGoat) from INE. A deliberately vulnerable Azure infrastructure.

### Google Cloud

- [GCPGoat](https://github.com/ine-labs/GCPGoat) from INE. A deliberately vulnerable GCP infrastructure.

### Multi-cloud and infrastructure as code

- [CNAPPGoat](https://github.com/tenable/cnappgoat) from Tenable. Vulnerable environments across AWS, Azure and GCP.
- [TerraGoat](https://github.com/bridgecrewio/terragoat) from Bridgecrew. Vulnerable Terraform, useful for practicing infrastructure as code review before anything gets deployed.
- [OWASP WrongSecrets](https://github.com/OWASP/wrongsecrets). Secrets handling mistakes across application, container, Kubernetes and cloud variants.

## Challenges

- [flAWS](http://flaws.cloud) and [flAWS 2](http://flaws2.cloud) by Scott Piper. Where a lot of us started with AWS security. flAWS 2 adds a defender path where you investigate the logs of the same attack.
- [The Big IAM Challenge](https://thebigiamchallenge.com) from Wiz. A series of IAM policy puzzles that reward reading policies carefully.
- [EKS Cluster Games](https://eksclustergames.com) from Wiz. You start in a low-privileged pod on EKS and work through real EKS misconfigurations.

## For defenders

- [Stratus Red Team](https://github.com/DataDog/stratus-red-team) from Datadog. Detonate individual cloud attack techniques in your own account and check whether your detections fire.
- [Pwned Labs defensive labs](https://pwnedlabs.io/explore) (ours). Investigate real attack activity with CloudTrail, Athena, GuardDuty and Splunk in hosted environments.

## Tools you will reach for

- [Pacu](https://github.com/RhinoSecurityLabs/pacu). The AWS exploitation framework from Rhino Security Labs.
- [CloudFox](https://github.com/BishopFox/cloudfox). Situational awareness for cloud penetration tests, from Bishop Fox.
- [PWNCLOUDOS](https://github.com/pwnedlabs/pwncloudos) (ours). A multi-cloud security Linux distribution with the tooling for AWS, Azure and Microsoft 365, and GCP and Google Workspace already installed.

## A path through the list

1. Get comfortable with the Linux command line and the basics of the cloud you want to learn, then learn its identity model properly: IAM in AWS, Entra ID and Azure RBAC, IAM and service accounts in GCP.
2. Work through the free hosted labs so you can focus on the technique instead of the setup.
3. Deploy CloudGoat or IAM Vulnerable and walk the same attack paths again without a guide.
4. Switch sides. Replay an attack with Stratus Red Team or a defensive lab and find it in the logs.
5. Prove it in a hands-on exam. Our bootcamps for [AWS (ACRTP)](https://pwnedlabs.io/bootcamps/placrtp-bootcamp), [Azure and Microsoft 365 (MCRTP)](https://pwnedlabs.io/bootcamps/mcrtp-bootcamp) and [Google Cloud (GCRTP)](https://pwnedlabs.io/bootcamps/gcrtp-bootcamp) each finish with a 24-hour practical exam in a live environment.

## Contributing

Open a pull request with the resource, a one-line description and whether it is free. We only list resources that are live and hands-on, and if a link breaks we will fix it or take it out.
