# Assignment1_Wandile-Mhlongo_CNP4

# Name: Wandile Mhlongo #
# Student Number: 222206314
# Subject: CNP4 Term 1 Assignment
# Due Date: 26/03/2026
# Repository: Assignment1_Wandile-Mhlongo_CNP4

### Creating of Instances and Security groups

![](https://github.com/Wandie23/Assignment1_Wandile-Mhlongo_CNP4/blob/16961ef80973c6f8a1651218107556ee54c6751a/Screenshot%202026-03-26%20211942.png)


![](https://github.com/Wandie23/Assignment1_Wandile-Mhlongo_CNP4/blob/7fdeac395a8ef01227864760ed50e7d030c8687d/Screenshot%202026-03-26%20211716.png)

### Preparation of Nodes

![](https://github.com/Wandie23/Assignment1_Wandile-Mhlongo_CNP4/blob/7e6d721791afa1f61653f27bf0e57a03dcea3870/c37585b5-d8b3-48dc-899d-0ead913a494f.png)

### Deploying of test application
![](https://github.com/Wandie23/Assignment1_Wandile-Mhlongo_CNP4/blob/65d76ae9e88e59a08c7642c16b563332023a1f5c/Screenshot%202026-03-25%20234032.png)

### Installation on NGINX Ingress Controller
![](https://github.com/Wandie23/Assignment1_Wandile-Mhlongo_CNP4/blob/bd9fc4ef995a78d0545e4a6b20ec20f8b1fdbccb/Screenshot%202026-03-26%20000345.png)

###  Creating of Storage
![](https://github.com/Wandie23/Assignment1_Wandile-Mhlongo_CNP4/blob/d55e4d961304130a7bccef80c8e7f78d860c1d46/Screenshot%202026-03-26%20002452.png)
### Uninstalling k3S
![](https://github.com/Wandie23/Assignment1_Wandile-Mhlongo_CNP4/blob/2e47154efdf14dbd56b41c39c9a7e80363ea3a4a/Screenshot%202026-03-26%20004452.png)


## Reflection

# What did i learn?

Deploying K3s on AWS allowed me to gain insight into the practical gap between theoretical Kubernetes understanding and real-world application. Prior to this assignment, I enjoyed a basic understanding of Kubernetes concepts such as control planes, pods, and services.

I also discovered the value of employing self-referencing security group rules for inter-node communication. This solution limits internal cluster communication to nodes in the same security group rather than exposing internal ports to the public internet, which improves security.

I also learned the process of  employing EC2 Instance Connect rather than standard SSH keys illustrated how cloud-native solutions may streamline operational procedures. Instead of handling private key files locally, I was able to connect to instances straight from the browser, which is very useful in controlled settings like AWS Learner Labs.


# What challenges did i face?

I ran across a deployment issue while attempting to build the security group during the EC2 instance launch. AWS does not enable a security group to reference itself if it does not already exist. The answer was to build the security group first and then choose it during the instance creation process.

When attempting to use a.ppk SSH key format in AWS CloudShell, which only accepts.pem keys. This required building a new key pair and knowing the distinction between PuTTY key format (.ppk) and OpenSSH format (.pem).

When attempting to join the second master node to the cluster, I noticed a token CA hash mismatch that proved to be one of the most important issues. The error notice "token CA hash does not match the Cluster CA certificate hash" was originally difficult to understand.I observed that the cluster token was wrongly inputted, with two characters swapped. To fix this problem, I removed K3s from the impacted node and carefully copied the right token from the primary master node.


