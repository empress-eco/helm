<div align="center">
<img src="https://grow.empress.eco/uploads/default/original/2X/1/1f1e1044d3864269d2a613577edb9763890422ab.png" alt="Project Logo">
<h1 align="center">Efficient Kubernetes Deployment with Helm</h1>
<p align="center">
Streamline your Kubernetes deployment using our robust Helm chart.
<br />
<a href="https://empress.eco/">Visit Our Website</a>
·
<a href="https://grow.empress.eco/">Get Support</a>
·
<a href="https://github.com/empress-eco/helm/issues">Report a Bug</a>
·
<a href="https://github.com/empress-eco/helm/issues">Request a Feature</a>
</p>
</div>

## About The Project

This Helm chart is crafted for developers striving for a more efficient and simplified deployment process on Kubernetes. It facilitates a comprehensive environment that mirrors a _Empress-bench_, offering optimized resource allocation and scaling to ensure smooth operations for your applications.

### Key Features
- Simplified deployment of ConfigMaps, Deployments, HorizontalPodAutoscalers, Ingresses, Jobs, PVC, Secrets, Services, and ServiceAccounts.
- Dynamic generation of `ingress` with custom name using `helm template`.
- Extensive job features including volume permissions fixing, db host configuring, site creation and dropping, backup and migration, and running custom commands.
- Efficient scaling of deployments with HorizontalPodAutoscalers.
- Persistent volume allocation for sites, config, and logs.

## Technical Stack and Setup Instructions

### Prerequisites
Ensure Helm is installed on your machine. If it isn't, refer to the [Helm installation guide](https://helm.sh/docs/intro/install/).

### Installation
Start by cloning this repository to your local machine
```sh
git clone https://github.com/empress-eco/helm.git
```
Navigate to the cloned directory and deploy the chart
```sh
helm install [NAME] [CHART] --namespace [NAMESPACE]
```

## Usage
Easily deploy your Kubernetes environment and make configuration adjustments to meet your specific needs. The Helm chart offers a user-centric, flexible, and efficient means to manage your resources.

## Contribution Guidelines
We warmly welcome contributions! To contribute:

- Fork the Project
- Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
- Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
- Push to the Branch (`git push origin feature/AmazingFeature`)
- Open a Pull Request

## License and Acknowledgements

### License
This project, including all contributions, is licensed under the MIT License.

### Acknowledgements
- Our heartfelt thanks go to all contributors and users who help to improve this Helm chart. Your efforts make a significant impact.
- Special thanks to [Empress](https://empress.eco/) for their continuous support.
- We express profound gratitude to the Empress Community, the architects of the essential tools powering this project. Their innovation and dedication have been instrumental in building the foundations and functionalities we rely on. We appreciate their pioneering work and ongoing support.

Visit [Empress GitHub](https://github.com/empress-eco/) for more information.