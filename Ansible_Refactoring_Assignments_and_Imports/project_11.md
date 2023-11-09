## Ansible Refactoring, Assignments and Imports


## Refactor ansible code by importing other playbooks into site.yml
### Step 1: Jenkins job enhancement
In the previous project, we create a jenkins build job, let us make some changes to our Jenkins job. Now every new change in the codes creates a separate directory which is not very convenient when we want to run some commands from one place. Besides, it consumes space on Jenkins serves with each subsequent change. Let us enhance it by introducing a new Jenkins project/job - we will require Copy Artifact plugin.

i. Go to your Jenkins-Ansible server and create a new directory called ansible-config-artifact - we will store there all artifacts after each build.
sudo mkdir /home/ubuntu/ansible-config-artifact

ii. Change permissions to this directory, so Jenkins could save files there - chmod -R 0777 /home/ubuntu/ansible-config-artifact

iii. Go to Jenkins web console -> Manage Jenkins -> Manage Plugins -> on Available tab search for Copy Artifact and install this plugin without restarting Jenkins.
iv. Create a new Freestyle project as it was done in the previous project and name it save_artifacts.

This project will be triggered by completion of your existing ansible project. Configure it accordingly
