<img src="https://github.com/Falc00n007/MulticloudK8sclusters4Gitlab/blob/main/multi-cloud-k8s-clustering-gitlab-frahimi.gif">

# multicloud k8s clustering for gitlab or Github

<p align="center"> 

<img src="https://kubernetes.io/images/nav_logo2.svg" width="210" style="margin-right: 10px;">
<img src="https://about.gitlab.com/images/press/logo/svg/gitlab-logo-200.svg" width="125" style="margin-right: 10px;">
<img src="https://www.iconsdb.com/icons/download/white/github-11-128.png" width="90" style="margin-right: 10px;">


# Introductions 

* GitLab provides a solution for managing Kubernetes clusters across multiple clouds in a centralized location. With GitLab, you can deploy, monitor, and manage your Kubernetes clusters with ease. This allows you to streamline your operations and reduce the complexity of managing multiple clusters across various cloud platforms. By leveraging GitLab's built-in CI/CD capabilities, you can automate your deployment processes and ensure that your applications are running smoothly on your Kubernetes clusters. Whether you're running a small-scale operation or a large enterprise, GitLab can help simplify your Kubernetes management and improve your overall productivity.
* As different form, for organizations that are adopting cloud-native architectures, managing multiple Kubernetes clusters effectively is essential. While both GitLab and GitHub are widely used platforms that offer a range of features, GitLab stands out as the better option for managing multiple Kubernetes clusters. This article will explain why GitLab is superior in this regard, highlighting its ability to simplify cluster management, foster structure, and promote collaboration through hierarchical groups. Additionally, we will examine the benefits of using GitLab's powerful templates to encapsulate the CI/CD pipeline code. By leveraging GitLab's features, organizations can streamline their Kubernetes workflows and improve their overall productivity and efficiency.

# which one, GitLab or GitHub?

When it comes to managing multiple Kubernetes clusters, GitLab is the superior choice compared to GitHub, despite both platforms offering a variety of useful features. With GitLab, you can seamlessly manage your manifests in a structured manner within a Git repository, making it easier to organize your clusters in multi-cloud environments using GitOps practices. Additionally, GitLab's hierarchy structure is highly flexible, allowing you to define unlimited groups, while GitHub has limitations that prevent the creation of hierarchical groups. This is one of the many reasons why GitLab is my preferred choice over GitHub for managing multiple Kubernetes clusters.

# 001- Creating GitLab Hierarchy Groups:
* To create GitLab Hierarchy Groups, you can define a group within another group, allowing you to inherit all of the parent group's environment variables. In doing so, you can define the KUBECONFIG file in the parent group, and use these variables in all projects within it. Consider a scenario where you have three Kubernetes clusters in different environments, such as AWS, Google Cloud, and Azure. To create a hierarchy that accommodates these clusters, you will need to create a group and project hierarchy in the following way:

<p align="center"> 
<img src="https://github.com/Falc00n007/MulticloudK8sclusters4Gitlab/blob/main/k8smulti-clusters.png">
<h6 align="center" >Organizing multiple Kubernetes clusters in a hierarchical structure using GitLab groups and subgroups.</h6>
</p>

* In this setup, there are multiple groups, each representing a separate Kubernetes cluster. Within each group, there are projects, which consist of a collection of manifest files specific to that project.
For instance, in the mentioned image, there is a project called API-GTWY located within the aws-us-east-2 group. This indicates that the manifest files within the API-GTWY project are designed for deployment to a Kubernetes cluster situated in the us-east region.

# 002- Storing KubeConfig in environment variables at the group level:
* In GitLab, projects belonging to a group can utilize shared environment variables defined at the parent group or higher levels, and the reverse is also true. To enable this functionality, you need to set up the KubeConfig file, which holds the necessary credentials for establishing a connection with the Kubernetes API server, in the group's settings. Navigate to the Group Name -> CI/CD Settings -> Variables -> Add Variable Path to configure it.

<p align="center"> 
<img src="https://github.com/Falc00n007/MulticloudK8sclusters4Gitlab/blob/main/kubeconfigfrtsst1245.png">
</p>

* In my specific situation, it is necessary to store the Kubeconfig files associated with my Kubernetes clusters in their corresponding groups.

# 003- Utilize GitLab CI to deploy your application.
* You now have the capability to generate manifest files within individual projects and deploy them using the GitLab CI pipeline. Below is an illustration of the content within the api-gateway project located in the aws-us-east-2 group as an example:
<pre>
.
├── gitlab-ci.yml
└── manifests
    ├── configmap.yaml
    ├── deployment.yaml
    └── service.yaml
</pre>
‍

  

#Continued! I am currently working on developing the documentation. It will take some time to complete. Please follow me for updates so that we can move forward together. Thank you.


