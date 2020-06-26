# Azure Arc Overview

<!-- For customers who want to simplify complex and distributed environments across on-premises, edge and multicloud, [Azure Arc](https://azure.microsoft.com/en-us/services/azure-arc/) enables deployment of Azure services anywhere and extends Azure management to any infrastructure. -->
オンプレミス、エッジ、マルチクラウドにまたがる複雑な分散環境を管理したいお客様のために、[Azure Arc](https://azure.microsoft.com/en-us/services/azure-arc/)はAzureの管理をあらゆるインフラストラクチャに拡張するものです。

<!-- * **Organize and govern across environments** - Get databases, Kubernetes clusters, and servers sprawling across on-premises, edge and multicloud environments under control by centrally organizing and governing from a single place. -->
* **システム全体を統合管理** -データベース、Kubernetesクラスタ、オンプレミス、エッジ、およびマルチクラウド環境にまたがるサーバを一元的に組織化し、単一の場所から管理することで、統合管理ができます。

<!-- * **Manage Kubernetes Apps at scale** - Deploy and manage Kubernetes applications across environments using DevOps techniques. Ensure that applications are deployed and configured from source control consistently. -->
* **大規模なKubernetesアプリケーションの管理** -DevOpsを使用して、環境全体にKubernetesアプリケーションをデプロイして管理します。これによりアプリケーションがソース管理から一貫してデプロイおよび管理できます。

<!-- * **Run data services anywhere** - Get automated patching, upgrades, security and scale on-demand across on-premises, edge and multicloud environments for your data estate. -->
* **どこでもデータサービスを実行** -自動化されたパッチ適用、アップグレード、セキュリティを取得し、オンプレミス、エッジ、およびマルチクラウド環境にわたってオンデマンドでデータ資産を拡張します。

# Azure Arc Story Time

<!-- Fabrikam Global Manufacturing runs workloads on different hardware, across on-premises datacenters, multiple public clouds, with Microsoft Azure being the main one as well as IoT workloads deployed on the edge. Workloads include very diverse services and are based on either virtual machines, managed Platforms-as-a-Service (PaaS) services as well as container-based applications.  -->
Fabrikam Global Manufacturing(仮想の企業)は、オンプレミスのデータセンター、複数のパブリッククラウドにわたって、さまざまなハードウェアでワークロードを実行しています。MicrosoftAzureが主なワークロードであり、IoTワークロードがエッジにデプロイされます。ワークロードには非常に多様なサービスが含まれ、仮想マシン、マネージドサービスとしてのプラットフォーム(PaaS)サービス、およびコンテナーベースのアプリケーションのいずれかに基づいています。
 
<!-- As mentioned, Fabrkam’s R&D teams are well-invested in containerized workloads for their modernized applications and as a result, they are using Kubernetes as their container orchestration platform, deployed both as a self-managed Kubernetes in their on-premises environments as well as a managed Kubernetes deployments in the cloud. -->
Fabrkam社のR＆Dチームは、最新のアプリケーションのコンテナー化されたワークロードに十分に投資し、コンテナオーケストレーションプラットフォームとしてKubernetesを使用しており、オンプレミス環境ではセルフマネージドKubernetesとして、またクラウドではマネージドKubernetesとしてデプロイしています。。

<!-- As part of their cloud-native practices with Azure being it’s main hyper-scale cloud, Fabrkam’s  operations teams are standardized and taking advantage of Azure Resource Manager (ARM) capabilities such as (but not limited to) tagging, Azure Monitoring for VMs and containers, logging and telemetry, policy and government, Desired State Configuration (DSC), Update Management, Change Tracking, Inventory management,etc.  -->
Fabrkam社の運用チームは、Azureをメインのハイパースケールクラウドとしたクラウドネイティブの実践の一環として、Azure Resource Manager (ARM)の機能を標準化し、タグ付け、VMとコンテナのAzure Monitoring、ロギングとテレメトリ、ポリシーとガバナンス、Desired State Configuration (DSC)、Update Management、Change Tracking、Inventory Managementなどの機能を活用しています。。

<!-- These practices and techniques are already well established for Azure-based workloads Fabrkam are using such as Azure VMs, Azure Kubernetes Service (AKS), Azure SQL, and many more. In order to take advantage of these well-established practices, Fabrkam are using Azure Arc to extend the ARM API’s to project and manage it’s workloads deployed outside of Azure. Once onboarded, Azure Arc projects resources as first-class citizens in Azure which can then take advantage of ARM capabilities mentioned above. In addition, they are able to guarantee Kubernetes deployments and app consistency through GitOps-based configuration for their Kubernetes clusters in Azure, other clouds and on-premises.  -->
これらのプラクティスやテクニックは、Azure VM、Azure Kubernetes Service (AKS)、Azure SQLなど、Fabrkam社がすでに使用しているAzureベースのワークロードで確立されています。これらの確立されたプラクティスを活用するために、Fabrkam社は**Azure Arc**を使用してARM APIを拡張し、Azureの外にデプロイされたワークロードをプロジェクト化して管理しています。一度オンボードされると、Azure ArcはAzureのリソースに対してARM機能を利用できます。さらに、Azure以外のクラウド、オンプレミス環境のKubernetesクラスタに対してもGitOpsベースの設定を行うことで、Kubernetesのデプロイとアプリの一貫性を保証できます。

 
<!-- With Azure Arc, Fabrikam are able to project resources and register them into Azure Resource Manager independently of where they run, so they have a single control plane and extend those cloud-native operations and governance beyond Azure. -->
Fabrikam社はAzure Arcを使用することで、リソースをプロジェクトし、実行場所に依存せずにAzure Resource Managerに登録できるため、単一のコントロールプレーンを持つことができ、クラウドネイティブな運用とガバナンスをAzure以外にも拡張できます。

<p align="center">
  <img src="img/architecture_dark.png" width="80%"/>
</p>

# Azure Arc "Jumpstart"

<!-- The following guides will walk you trough on how to demo and get started with Azure Arc. They are designed with a "zero to hero" approach in mind and with much automation as possible. The goal is for you to have a working Azure Arc demo environment spined-up in no time so you can focus on showing the core values of the solution. -->
次のガイドでは、Azure Arcのデモを開始する方法について説明します。 「zero to hero」のアプローチを念頭に置いて設計されており、可能な限り手順は自動化されています。この目標はすぐに機能するAzure Arcデモ環境を準備して、ソリューションのコアバリューの表示に集中できるようにすることです。

<!-- **Disclaimer: The intention for this repo is to focus on the core Azure Arc capabilities. deployment scenarios, use-cases and ease of use. It does not focus on Azure best-practices or the other tech and OSS project being leveraged in the guides and code.** -->
**免責事項：このリポジトリの目的は、Azure Arc のコア機能、デプロイシナリオ、ユースケース、使いやすさに焦点を当てています。Azure のベストプラクティスや、ガイドやコードで活用されている他の技術や OSS プロジェクトには焦点を当てていません。**

## Azure Arc for Servers
<!-- The below deployment options are focusing on Azure Arc for Servers. It is designed to quickly spin up a server that is ready to be projected in Azure Arc and for you to start playing with it.  -->
以下のデプロイオプションは、Azure Arc for Serversに焦点を当てています。これは、Azure Arcで管理する準備ができているサーバーを素早くスピンアップして、それを使って検証ができるように設計されています。

<!-- **Note: For a list of supported operating systems and Azure regions, please visit the official [Azure Arc docs](https://docs.microsoft.com/en-us/azure/azure-arc/servers/overview).** -->
**注：サポートされているオペレーティングシステムとAzureリージョンのリストについては、公式の[Azure Arc docs](https://docs.microsoft.com/en-us/azure/azure-arc/servers/overview)を参照してください。**

#### General

<!-- * [Connect an existing Linux server to Azure Arc](azure_arc_servers_jumpstart/docs/onboard_server_linux.md) -->
* [既存のLinuxサーバーをAzure Arcに接続する](azure_arc_servers_jumpstart/docs/onboard_server_linux.md)

<!-- * [Connect an existing Windows machine to Azure Arc](azure_arc_servers_jumpstart/docs/onboard_server_win.md) -->
* [既存のWindowsマシンをAzure Arcに接続する](azure_arc_servers_jumpstart/docs/onboard_server_win.md)

#### Vagrant

<!-- * [Deploy a local Ubuntu VM and connect it to Azure Arc using Vagrant](azure_arc_servers_jumpstart/docs/local_vagrant_ubuntu.md) -->
* [Vagrantを使用してUbuntu VMをデプロイし、Azure Arcに接続する](azure_arc_servers_jumpstart/docs/local_vagrant_ubuntu.md)

<!-- * [Deploy a local Windows 10 VM and connect it to Azure Arc using Vagrant](azure_arc_servers_jumpstart/docs/local_vagrant_windows.md) -->
* [Vagrantを使用してWindows 10 VMをデプロイし、Azure Arcに接続する](azure_arc_servers_jumpstart/docs/local_vagrant_windows.md)

#### Amazon Web Services (AWS)

<!-- * [Deploy an AWS EC2, Ubuntu VM and connect it to Azure Arc using Terraform](azure_arc_servers_jumpstart/docs/aws_terraform_ubuntu.md) -->
* [AWS EC2、Ubuntu VMをデプロイし、Terraformを使用してAzure Arcに接続する](azure_arc_servers_jumpstart/docs/aws_terraform_ubuntu.md)

* [Deploy an AWS Amazon Linux 2 VM and connect it to Azure Arc using Terraform](azure_arc_servers_jumpstart/docs/aws_terraform_al2.md)

#### Google Cloud Platform (GCP)

<!-- * [Deploy a GCP, Ubuntu VM and connect it to Azure Arc using Terraform](azure_arc_servers_jumpstart/docs/gcp_terraform_ubuntu.md) -->
* [GCP、Ubuntu VMをデプロイし、Terraformを使用してAzure Arcに接続する](azure_arc_servers_jumpstart/docs/gcp_terraform_ubuntu.md)

<!-- * [Deploy a GCP, Windows Server VM and connect it to Azure Arc using Terraform](azure_arc_servers_jumpstart/docs/gcp_terraform_windows.md) -->
* [GCP、Windows Server VMをデプロイし、Terraformを使用してAzure Arcに接続する](azure_arc_servers_jumpstart/docs/gcp_terraform_windows.md)

#### VMware

<!-- * [Deploy a VMware vSphere, Ubuntu Server VM and connect it to Azure Arc using Terraform](azure_arc_servers_jumpstart/docs/vmware_terraform_ubuntu.md) -->
* [VMware vSphere、Ubuntu Server VMをデプロイし、Terraformを使用してAzure Arcに接続する](azure_arc_servers_jumpstart/docs/vmware_terraform_ubuntu.md)

<!-- * [Deploy a VMware vSphere, Windows Server VM and connect it to Azure Arc using Terraform](azure_arc_servers_jumpstart/docs/vmware_terraform_winsrv.md) -->
* [VMware vSphere、Windows Server VMをデプロイし、Terraformを使用してそれをAzure Arcに接続する](azure_arc_servers_jumpstart/docs/vmware_terraform_winsrv.md)



#### Azure Arc for Servers - 2日目のシナリオとユースケース

<!-- * [Tagging and querying server inventory across multiple clouds using Resource Graph Explorer](azure_arc_servers_jumpstart/docs/arc_inventory_tagging.md) -->
* [リソースグラフエクスプローラーを使用した複数のクラウドにわたるサーバーインベントリのタグ付けとクエリ](azure_arc_servers_jumpstart/docs/arc_inventory_tagging.md)

<!-- * [Deploying Microsoft Monitoring Agent Extension (MMA) to Azure Arc Linux and Windows VMs using Extension Management](azure_arc_servers_jumpstart/docs/arc_vm_extension_mma_arm.md) -->
* [Extension Managementを使用してMicrosoft Monitoring Agent Extension (MMA) をAzure Arc LinuxおよびWindows VMにデプロイする](azure_arc_servers_jumpstart/docs/arc_vm_extension_mma_arm.md)

<!-- * [Deploying Custom Script Extension to Azure Arc Linux and Windows VMs using Extension Management](azure_arc_servers_jumpstart/docs/arc_vm_extension_customscript_arm.md) -->
* [Extension Managementを使用してカスタムスクリプト拡張をAzure Arc LinuxおよびWindows VMにデプロイする](azure_arc_servers_jumpstart/docs/arc_vm_extension_customscript_arm.md)

<!-- * [Deploying Microsoft Monitoring Agent Extension (MMA) to Azure Arc Linux and Windows VMs using Azure Policies](azure_arc_servers_jumpstart/docs/arc_policies_mma.md) -->
* [Azureポリシーを使用してMicrosoft Monitoring Agent Extension（MMA）をAzure Arc LinuxおよびWindows VMにデプロイする](azure_arc_servers_jumpstart/docs/arc_policies_mma.md)

## Azure Arc for Kubernetes

<!-- The below deployment options are focusing on Azure Arc for Kubernetes. It is designed to quickly spin up a Kubernetes cluster that is ready to be projected in Azure Arc and for you to start playing with.  -->
以下のデプロイオプションは、Azure Arc for Kubernetesに重点を置いています。これは、Azure Arcに接続する準備ができているKubernetesクラスターをすばやく起動し、ユーザーが操作を開始できるように設計されています。

#### General

<!-- * [Connect an existing Kubernetes cluster to Azure Arc](azure_arc_k8s_jumpstart/docs/onboard_k8s.md) -->
* [既存のKubernetesクラスターをAzure Arcに接続する](azure_arc_k8s_jumpstart/docs/onboard_k8s.md)

#### Azure Kubernetes Service (AKS)

<!-- * [Deploy AKS cluster and connect it to Azure Arc using Azure ARM template](azure_arc_k8s_jumpstart/docs/aks_arm_template.md) -->
* [AKSクラスターをデプロイし、Azure ARMテンプレートを使用してAzure Arcに接続する](azure_arc_k8s_jumpstart/docs/aks_arm_template.md)

<!-- * [Deploy AKS cluster and connect it to Azure Arc using Terraform](azure_arc_k8s_jumpstart/docs/aks_terraform.md) -->
* [AKSクラスターをデプロイし、Terraformを使用してAzure Arcに接続する](azure_arc_k8s_jumpstart/docs/aks_terraform.md)

<!-- * [Deploy GitOps configurations and perform basic GitOps flow on AKS as an Azure Arc Connected Cluster](azure_arc_k8s_jumpstart/docs/aks_gitops.md) -->
* [GitOps構成を展開し、Azure Arc ConnectedクラスターとしてAKSで基本的なGitOpsフローを実行する](azure_arc_k8s_jumpstart/docs/aks_gitops.md)

#### Amazon Elastic Kubernetes Service (EKS)

<!-- * [Deploy EKS cluster and connect it to Azure Arc using Terraform](azure_arc_k8s_jumpstart/docs/eks_terraform.md) -->
* [EKSクラスターをデプロイし、Terraformを使用してAzure Arcに接続する](azure_arc_k8s_jumpstart/docs/eks_terraform.md)

#### Google Kubernetes Engine (GKE)

<!-- * [Deploy GKE cluster and connect it to Azure Arc using Terraform](azure_arc_k8s_jumpstart/docs/gke_terraform.md) -->
* [GKEクラスターをデプロイし、Terraformを使用してAzure Arcに接続します](azure_arc_k8s_jumpstart/docs/gke_terraform.md)

#### Rancher k3s

<!-- * [Deploy Rancher k3s on an Azure VM and connect it to Azure Arc using Azure ARM template](azure_arc_k8s_jumpstart/docs/rancher_k3s_azure_arm_template.md) -->
* [Azure VMにRancher k3sをデプロイし、Azure ARMテンプレートを使用してAzure Arcに接続する](azure_arc_k8s_jumpstart/docs/rancher_k3s_azure_arm_template.md)

<!-- * [Deploy Rancher k3s on an Azure VM and connect it to Azure Arc using Terraform](azure_arc_k8s_jumpstart/docs/rancher_k3s_azure_terraform.md) -->
* [Rancher k3sをAzure VMにデプロイし、Terraformを使用してAzure Arcに接続します](azure_arc_k8s_jumpstart/docs/rancher_k3s_azure_terraform.md)

<!-- * [Deploy Rancher k3s on a VMware vSphere VM and connect it to Azure Arc using Terraform](azure_arc_k8s_jumpstart/docs/rancher_k3s_vmware_terraform.md) -->
* [Rancher k3sをVMware vSphere VMにデプロイし、Terraformを使用してAzure Arcに接続する](azure_arc_k8s_jumpstart/docs/rancher_k3s_vmware_terraform.md)

#### Azure Red Hat OpenShift V4
<!-- * [Deploy Azure Redhat Openshift Cluster and connect it to Azure Arc using automation](azure_arc_k8s_jumpstart/docs/aro_script.md) -->
* [Azure Red Hat Openshift Clusterをデプロイし、オートメーションを使用してAzure Arcに接続する](azure_arc_k8s_jumpstart/docs/aro_script.md)


#### Azure Arc for Kubernetes - 2日目のシナリオとユースケース

<!-- * [Deploy GitOps configurations and perform basic GitOps flow on AKS as an Azure Arc Connected Cluster](azure_arc_k8s_jumpstart/docs/aks_gitops.md) -->
* [GitOps構成をデプロイし、Azure Arc ConnectedクラスターとしてAKSでGitOpsフローを実行する](azure_arc_k8s_jumpstart/docs/aks_gitops.md)

<!-- * [Integrate Azure Monitor for Containers with AKS as an Azure Arc Connected Cluster](azure_arc_k8s_jumpstart/docs/aks_monitor.md) -->
* [Azure Monitor for ContainersをAzure Arcに接続したAKSクラスターと統合する](azure_arc_k8s_jumpstart/docs/aks_monitor.md)

<!-- * [Apply GitOps configurations on AKS as an Azure Arc Connected Cluster using Azure Policy for Kubernetes ](azure_arc_k8s_jumpstart/docs/aks_policy.md) -->
* [Kubernetes用のAzure Policyを使用して、AKSにGitOps構成をAzure Arc Connected Clusterとして適用する](azure_arc_k8s_jumpstart/docs/aks_policy.md)

<!-- * [Deploy GitOps configurations and perform basic GitOps flow on GKE as an Azure Arc Connected Cluster](azure_arc_k8s_jumpstart/docs/gke_gitops.md) -->
* [GitOps構成をデプロイし、Azure Arc Connected ClusterとしてGKEでGitOpsフローを実行する](azure_arc_k8s_jumpstart/docs/gke_gitops.md)

<!-- * [Integrate Azure Monitor for Containers with GKE as an Azure Arc Connected Cluster](azure_arc_k8s_jumpstart/docs/gke_monitor.md) -->
* [Azure Monitor for ContainersをAzure Arc Connected ClusterとしてGKEと統合する](azure_arc_k8s_jumpstart/docs/gke_monitor.md)

<!-- * [Apply GitOps configurations on GKE as an Azure Arc Connected Cluster using Azure Policy for Kubernetes ](azure_arc_k8s_jumpstart/docs/gke_policy.md) -->
* [Kubernetes用のAzure Policyを使用して、Azure Arc Connected ClusterとしてGKEにGitOps構成を適用する](azure_arc_k8s_jumpstart/docs/gke_policy.md)

## Azure Arc for Data Services

Coming soon!

# Support for future deployment scenarios

<!-- Below are an additional deployment scenarios the team is currently working on. -->
以下は、チームが取り組んでいる追加の展開シナリオです。

### Azure Arc for Servers

<!-- - Support for a Windows Server AWS EC2 instance deployment using Terraform -->
- Terraformを使用したWindows Server AWS EC2インスタンス デプロイのサポート

### Azure Arc for Kubernetes

<!-- - Support for kind Deployment guide with Arc connectivity -->
- kindのAzure Arc接続導入ガイドのサポート
<!-- - Support for Minikube Deployment guide with Arc connectivity -->
- MinikubeのAzure Arc接続導入ガイドのサポート
<!-- - Support for MicroK8s Deployment guide with Arc connectivity -->
- Microk8sのAzure Arc接続導入ガイドのサポート

### Azure Arc for Data Services

<!-- - Support SQL Managed Instance (MI) in Azure Kubernetes Service (AKS) deployment using ARM template -->
- ARMテンプレートを使用したAzure Kubernetes Service(AKS)デプロイメントでのSQLマネージドインスタンス(MI)のサポート
<!-- - Support SQL Managed Instance (MI) in Azure Kubernetes Service (AKS) deployment using Terraform -->
- Terraformを使用したAzure Kubernetes Service(AKS)デプロイメントでのSQLマネージドインスタンス(MI)のサポート
<!-- - Support PostgreSQL Hyperscale in Azure Kubernetes Service (AKS) deployment using ARM template -->
- ARMテンプレートを使用したAzure Kubernetes Service(AKS)デプロイメントでのPostgreSQLハイパースケールのサポート
<!-- - Support PostgreSQL Hyperscale in Azure Kubernetes Service (AKS) deployment using Terraform -->
- Terraformを使用したAzure Kubernetes Service(AKS)デプロイメントでのPostgreSQLハイパースケールのサポート

## Contributing

<!-- Before contributing code, please see the [CONTRIBUTING](CONTRIBUTING.md) guide. -->
コードを提供する前に、[CONTRIBUTING]（CONTRIBUTING.md）ガイドをご覧ください。
<!-- Issues, PRs and Feature Request have their own templates. Please fill out the whole template. -->
問題、PR、機能リクエストには独自のテンプレートがあります。テンプレート全体に記入してください。