# Ansible Playbook for Setting Up a Kubernetes Cluster

This repository contains an Ansible playbook designed to automate the setup of a Kubernetes cluster. The playbook is divided into two main sections: one for setting up the master node(s) and another for joining worker nodes to the cluster.

## Prerequisites

Before running this playbook, ensure you have the following installed and configured:

- **Ansible**: Ensure you have Ansible installed on your control node. You can install Ansible using pip:

- **SSH Access**: Your control node must have SSH access to all target nodes (both master and worker nodes).

- **Ansible Inventory File**: Create an inventory file (`hosts.ini`) listing your master and worker nodes. Here's an example structure:

- **Docker**: The playbook installs Docker on both master and worker nodes. Ensure your nodes meet the Docker system requirements.

## Getting Started

### Step 1: Update the Inventory File

Update the `hosts.ini` file with the correct IP addresses or hostnames of your master and worker nodes.

### Step 2: Run the Playbook

Navigate to the directory containing your `playbook.yaml` and run the following commands:

#### For Master Node Setup

Run the playbook for initializing the Kubernetes master node:

ansible-playbook -i hosts.ini playbook.yaml -l masters


#### For Worker Nodes Joining

After successfully setting up the master node, run the playbook to join worker nodes to the cluster:

ansible-playbook -i hosts.ini playbook.yaml -l workers

## Post-Setup Steps

Once the playbook completes execution, you should have a functional Kubernetes cluster. You can verify the cluster status by accessing the Kubernetes API server through `kubectl`.

## Troubleshooting

If you encounter issues during the setup, check the output logs generated by the playbook tasks for errors. Common issues include network connectivity problems between nodes or missing dependencies.

## Contributing

Contributions to improve this playbook are welcome. Please submit pull requests or open issues with detailed descriptions of the changes or issues encountered.