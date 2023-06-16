# Kubernetes with Tanzu Cheatsheet

## Introduction
Welcome to a place where you will hopefully speed up your work with Tanzu and Kubernetes. The intention is provide a structural approach to the Day 0-n lifecycle as for its commands as well as do's, why's and dont's. This cheatsheet will primarily focus on Tanzu Kubernetes Grid (TKG) and Kubernetes in a joint view on managing modern apps in a cloud native way. The page will try to always keep the latest modern approaches to the different scenarios and commands as available per latest released versions.

The approach for the content below is simple. The *italic* areas Platform, App, and Data is probably what you are familiar with when it comes to traditional IT environments where you have a platform or environment that some application is running on where a business or some end user needs in order to handle data. Always try to think in this order (i.e. Platform -> App -> Data) for this cheatsheet as it will ease your way throughout the DevSecOps lifecycle. Once familiar with the basics you will be able to move on applying a more cloud native way of thinking to modern apps.

### Table of Content
| | [Day 0 - Spinning up needed resources](Day%200%20-%20Spinning%20up%20needed%20resources) | [Day 1 - Design buildup](Day%201%20-%20Design%20buildup) | [Day 2 - Post deployment Ops](Day%202%20-%20Post%20deployment%20Ops)| [Day *n* - ..and the fun begins](Day%20n%20-%20Next%20steps) |
| :---: | :---: | :---: | :---: | :---: |
| *App* | <sub>Bare minimum working app</sub> | <sub>Version 0.1 / MVP</sub> | <sub>Version 1.0 / Release including dependencies and resources</sub> | <sub>Tanzu Application Platform</sub> |
| **Dev** | <sub>Key abstractions defined<br />From code to image</sub> | <sub>Platform MVP<br />[<sub>TAP install</sub>](Day%201%20-%20Design%20buildup/TAP%20install/README.md) | <sub>Golden paths?<br />Multiple dev projects in TAP</sub> | <sub>Including edge</sub> |
| *Data* | <sub>Expose XX</sub>  |  <sub>Install Greenplum<br />Install RabbitMQ</sub> | <sub>Making use of data more efficiently<br />Data Centric Pipelines</sub>  | <sub>TDI</sub> |
| **Sec** | <sub>Basic rules and principles</sub>  | <sub>XX</sub>  |  <sub>Using TAP and TKO in symbiosis</sub> | <sub>XX</sub> |
| *Platform* | [<sub>Install Kubernetes/TKG on local machine</sub>](Day%200%20-%20Spinning%20up%20needed%20resources/Local%20Kubernetes) | <sub><br /> Install TKG on vSphere <br /> Install Kubernetes/TKG on Azure <br /> Install Kubernetes/TKG on AWS <br /> Install Kubernetes/TKG on Google Cloud </sub>  |  <sub>Configuring access to clusters</sub> | <sub>XX</sub> |
| **Ops** | <sub>Create your first cluster<br />Basic metrics with XYZ</sub>  | <sub>Installing TKO</sub>  | <sub>Managing multi-cloud aspects with TKO</sub>  | <sub>Providing managed services with TKO</sub> |

<details><summary>Abbreviations</summary>
<p>
  <ul>
    <li><i>DevSecOps</i> - Development Security Operations for XX</li>
    <li><i>MVP</i> - Minimal Viable Product</li>
    <li><i>TAP</i> - Tanzu Application Platform</li>
    <li><i>TKG</i> - Tanzu Kubernetes Grid</li>
    <li><i>TKO</i> - Tanzu for Kubernetes Operations</li>
  </ul>
    </p>
</details>
