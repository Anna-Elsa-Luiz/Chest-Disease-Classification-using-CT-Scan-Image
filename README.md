
# **CHEST DISEASE CLASSIFICATION USING CT-SCAN**


<h2>Overview</h2>
<p>
This project aims to develop an AI model capable of classifying and diagnosing chest cancer, with a specific focus on adenocarcinoma, the most prevalent form of lung cancer. Leveraging deep learning techniques, particularly Convolutional Neural Networks (CNNs), the model utilizes the pretrained VGG-16 architecture to analyze medical images for cancer detection. The primary objective is to assist healthcare professionals in achieving early and accurate diagnoses, ultimately leading to improved patient outcomes.
</p>



<h2>Model Architecture</h2>
<p>The VGG-16 model is a deep convolutional neural network renowned for its effectiveness in image classification tasks. Pretrained on large-scale image datasets such as ImageNet, VGG-16 possesses a deep network architecture consisting of 16 layers, including convolutional layers with small 3x3 filters and max-pooling layers. By fine-tuning the pretrained VGG-16 model on chest cancer images, we aim to capitalize on its robust feature extraction capabilities for accurate cancer classification.</p>



<h2>Usage</h2>
<p>Healthcare professionals can utilize the developed AI model as a supplementary tool in chest cancer diagnosis. By inputting medical images into the pretrained VGG-16 model, clinicians can receive automated predictions regarding the presence of adenocarcinoma, facilitating timely intervention and treatment planning.</p>


<h2>Benefits</h2>
<ul>
    <li>Early Detection: The AI model enables early detection of chest cancer, particularly adenocarcinoma, which is crucial for improving patient prognosis.</li>
    <li>Accuracy: By leveraging deep learning techniques and pretrained models like VGG-16, the model achieves high levels of accuracy in cancer classification.</li>
    <li>Efficiency: Automated classification of medical images streamlines the diagnostic process, allowing healthcare professionals to focus on patient care and treatment decisions.</li>
</ul>




<h2>MLOps Implemented</h2>
<ul>
    <li>MLFlow: Experiment Tracking</li>
    <li>DVC/Data Version Control: Pipeline Tracking</li>
</ul>



<h2>Deployment</h2>
<p>Using Jenkins and AWS EC2, ECR</p>








------------------------------------------------
## **Project Implementation**


<ul>
  <li>Create an acc in local repo and connect it with the github</li>
  <li>Then create the READMe.md, .gitignore, LICENSE files</li>
  <li>Then create the template.py file</li>
  <li>Created the env and activated</li>
  <li>We are going to write the constants in yaml file instead of constants</li>
  <li>Edit the requirements.txt file and setup.py file</li>
  <li>Python-box is also used to manage the exception</li>
  <li>Here custom logging is written on the constructor file in src/cnnclassifier. By doing this, no need to mention the logger folder (first approach)</li>
  <li>You can also do it in another way of creating the logging folder and inside the folder create a constructor file, write the code (second approach)</li>
  <li>Create a common.py file inside the utils → code</li>
  <li>Configbox: to make it easily callable (refer trails.ipynb)</li>
  <li>Ensure_annotation: make it bug free (refer trails.ipynb)</li>
</ul>



<h2>Workflows</h2>
<ul>
  <li>Update the config.yaml</li>
  <li>Update params.yaml</li>
  <li>Update the entity</li>
  <li>Update the configuration manager in src config</li>
  <li>Update the components</li>
  <li>Update the pipeline</li>
  <li>Update the main.py</li>
  <li>Update the dvc.yaml</li>
</ul>




<h2>Mlflow --> Experiment Tracking : </h2>

Example :

ElasticNet : parameters (alpha , L1 ) 
                    0.7 , 0.9 --> exp 1 :70%
                    0.5 , 0.5 --> exp 2 :80%
                    0.4 , 0.6 --> exp 3 :50%
CSV Exp 1 , Exp 2 , Exp 3 



<h2>DagsHub</h2>
<ol>
  <li>Create a repo in GitHub</li>
  <li>Go to DagsHub</li>
  <li>Create a new repository</li>
  <li>Connect to repo</li>
  <li>GitHub</li>
  <li>Connect to the repo</li>
</ol>

<p>Copy the experiment tracking to the README file in GitHub:</p>
<pre>
MLFLOW_TRACKING_URI=https://dagshub.com/-------/mlflow_demo.mlflow \
MLFLOW_TRACKING_USERNAME=------ \
MLFLOW_TRACKING_PASSWORD=------3a547cee2bfa163992db880d6b571b70 \
python script.py
</pre>

<pre>
export MLFLOW_TRACKING_URI=https://dagshub.com/-----/mlflow_demo.mlflow 
export MLFLOW_TRACKING_USERNAME=-------- 
export MLFLOW_TRACKING_PASSWORD=------63a547cee2bfa163992db880d6b571b70
</pre>




<h2>How to select the good one among many?</h2>
<ol>
  <li>Select every experiments</li>
  <li>Compare</li>
  <li>We get a parallel coordinate plot</li>
</ol>

<p>Criteria for selecting the best model:</p>
<ul>
  <li>Accuracy wise: r2 (It should be high)</li>
  <li>Mean Absolute Error (MAE): should be low</li>
  <li>Root Mean Squared Error (RMSE): should be low</li>
</ul>

<p>Thus instead of performing hyperparameter tuning on DL model (which is costly and time-taking task), we could simply compare and obtain the best model from MLflow - DagsHub.</p>



<h2>Components</h2>
<h3>Data Ingestion</h3>
<ul>
  <li>Upload the data in the drive and download it using gdown</li>
  <li>Now in config → config.yaml: code</li>
  <li>Create a data ingestion file in the research folder</li>
  <li>Now update the entity: which is the return type of the function → create config_entity.py</li>
  <li>Update the config → configuration.py</li>
  <li>Now the component → create a file: data_ingestion.py</li>
  <li>Now update the pipeline</li>
  <li>Update the endpoint → main.py</li>
  <li>Update the utils → common.py</li>
</ul>


<h3>Create a base model</h3>
<ul>
  <li>Update the config.yaml file: prepare_base_model</li>
  <li>Params.yaml</li>
  <li>Update the preparebasemodel.ipynb</li>
  <li>Entity → config entity</li>
  <li>Then update the config → configuration manager</li>
  <li>Components → create a file prepare_base_model.py</li>
  <li>Update the pipeline</li>
  <li>Then the endpoint: main.py</li>
</ul>



<h3>Model Trainer</h3>
<ul>
  <li>Create a file modeltrainer.ipynb and update it</li>
  <li>Entity → configentity.py</li>
  <li>Config → configuration.py</li>
  <li>Components → create a file: modeltrainer.py</li>
  <li>Update the pipeline</li>
  <li>Then the endpoint: main.py</li>
</ul>


<h3>Model Evaluation using MLflow</h3>
<ul>
  <li>Config is not required here</li>
  <li>Create an ipynb file model evaluation with MLflow</li>
  <li>Connect the repo to DagsHub</li>
  <li>Then MLflow tracking in bash</li>
</ul>


<p>In Jupyter Notebook:</p>
<pre>
os.environ["MLFLOW_TRACKING_URI"]="https://dagshub.com/------/Chest-Disease-Classification-using-CT-Scan-Image.mlflow"
os.environ["MLFLOW_TRACKING_USERNAME"]="------"
os.environ["MLFLOW_TRACKING_PASSWORD"]="------63a547cee2bfa163992db880d6b571b70”
</pre>



<ul>
  <li>Update the entity</li>
  <li>Config → configuration</li>
  <li>Components → model evaluation</li>
  <li>Pipeline</li>
  <li>End point → main.py</li>
</ul>




<ul>
  <li>Dvc.yaml → Update the file</li>
  <li>Now execute the commands</li>
  <li>Execute Dvc init (dvc folder has been created)</li>
  <li>Execute DVC repro</li>
  <li>In dvc.lock file → it has saved all the metadata</li>
  <li>If you execute the dvc repro it will show:</li>
</ul>
<pre>
Stage 'data_ingestion' didn't change, skipping
Stage 'prepare_base_model' didn't change, skipping
Stage 'training' didn't change, skipping
Stage 'evaluation' didn't change, skipping
Data and pipelines are up to date.
</pre>



<h2>Prediction pipeline</h2>
<ul>
  <li>Prediction.py file added</li>
  <li>Create a folder → model → copy the model during training</li>
  <li>Push the changes to GitHub</li>
</ul>



<h2>User App</h2>
<ul>
  <li>Create the index.html</li>
  <li>And app.py using Flask</li>
</ul>



<h2>Deployment</h2>
<ul>
  <li>Create a Dockerfile</li>
  <li>.dockerignore</li>
  <li>Docker-compose.yml</li>
  <li>Create a .jenkins folder → then inside that create a Jenkinsfile</li>
  <li>Scripts → ec2_instance.sh, Jenkins.sh files created</li>
</ul>



<h2>Deployment</h2>
<ul>
  <li>Create a Dockerfile</li>
  <li>.dockerignore</li>
  <li>Docker-compose.yml</li>
  <li>Create a .jenkins folder → then inside that create a Jenkinsfile</li>
  <li>Scripts → ec2_instance.sh, Jenkins.sh files created</li>
</ul>


<h2>AWS</h2>
<p>AWS login</p>
<ul>
  <li>Create IAM user:</li>
  <li>IAM → User → Create user → User name: chest-user → Permission policy: Administrator access → Create user</li>
</ul>



<h2>Setup the security credential</h2>
<p>Security credential → create access keys → command line interface → permission → create access keys: download as CSV</p>

<p>Now we need to launch a Jenkins Server: here EC2</p>

<ul>
  <li>EC2 → Launch instance</li>
  <li>Name: jenkin-machine → Ubuntu → Amazon Machine Image → Instance type: → Create key pair → Launch instance</li>
  <li>Take the instance created → connect</li>
</ul>



<h3>Now we need to setup the Jenkins</h3>

<pre>#!/bin/bash

sudo apt update

sudo apt install openjdk-8-jdk -y

wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -

sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

sudo apt-get update

sudo apt-get install jenkins -y

sudo systemctl start jenkins

sudo systemctl enable jenkins

sudo systemctl status jenkins

## Installing Docker

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker $USER

sudo usermod -aG docker jenkins

newgrp docker

sudo apt install awscli -y

sudo usermod -a -G docker jenkins

## AWS configuration & restarts jenkins

aws configure

sudo systemctl restart jenkins

## Now setup elastic IP on AWS

## For getting the admin password for jenkins

sudo cat /var/lib/jenkins/secrets/initialAdminPassword
</pre>



<h2>Setting the Elastic IP</h2>
<ul>
  <li>Allocate Elastic IP address → keep it as default → allocate</li>
  <li>Associate this elastic IP address → instance → select the instance → Associate</li>
  <li>Select the instance → security → security groups → edit inbound rules → add rules → 8080 & 0.0.0.0/0</li>
  <li>Copy the public IP and load in a new page → Jenkins will be running → administrator password: paste → continue</li>
  <li>For administrator password: execute sudo cat /var/lib/jenkins/secrets/initialAdminPassword in EC2 terminal</li>
  <li>Install suggested plugins → automatically installing required items → create First admin user</li>
  <li>Username: , password: , full name: , email: → save and finish → obtain the URL for Jenkins → Log into Jenkins Server</li>
</ul>

<p>Now we have to set the secret variable in Jenkins server:</p>
<ul>
  <li>Manage Jenkins → credentials → system → global credentials → add credential → secret text → ECR_REPOSITORY:</li>
</ul>



<h2>Create an ECR repo in AWS</h2>
<ul>
  <li>AWS → ECR → create repo → private → name → create</li>
  <li>Copy the URI → paste in the Jenkins server: ECR_REPOSITORY</li>
</ul>

<h2>Next secret variable:</h2>
<ul>
  <li>Secret text → Global → AWS_ACCOUNT_ID: copy the ID from AWS account</li>
  <li>Secret text → Global → AWS_ACCESS_KEY_ID: copy from the downloaded CSV</li>
  <li>Secret text → Global → AWS_SECRET_ACCESS_KEY: copy from the downloaded CSV</li>
  <li>SSH Username with private key → Global → ssh_key → Enter directly → add → copy the PEM file</li>
</ul>

<p>Dashboard → Manage Jenkins → Plugins → Available plugins → SSH agents → install → install and restart → Again log into Jenkins server → verify whether the credentials are added</p>

<p>Now create a pipeline:</p>
<ul>
  <li>New item → Pipeline name → Pipeline → okay → Pipeline script from SCM → SCM: Git → paste the repo URL → branch: main → path of Jenkinsfile → save</li>
</ul>

<p>Now we have to create another EC2 instance for the application:</p>
<ul>
  <li>EC2 → instance → Launch instance → Name: → Ubuntu → t2large → key value pair for the EC2 -1 → 32 GB → launch instance</li>
</ul>


<h2>Instance → Connect</h2>

<pre>#!/bin/bash

sudo apt update

sudo apt-get update

sudo apt upgrade -y

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker $USER

newgrp docker

sudo apt install awscli -y

## AWS configuration

aws configure

## Now setup elastic IP on AWS
</pre>


<p>Run it on the EC2-2 instance terminal</p>
<pre>
sudo apt update
sudo apt-get update
sudo apt upgrade -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER
newgrp docker
sudo apt install awscli -y

## AWS configuration
aws configure

## Now setup elastic IP on AWS
</pre>

<p>Now create an Elastic IP for the EC2-2 instance:</p>
<ul>
  <li>Allocate Elastic IP address → allocate → Associate Elastic IP address → Associate for the EC2-2 instance</li>
</ul>

<p>Now open up the Jenkinsfile → change the public IP near the ssh_key from the EC2-2 instance</p>

<p>Now create a folder .github → create another folder inside → workflows → create a file: main.yaml → copy the code</p>

<p>Now in GitHub → settings → secrets and variables → actions → create new repository secret:</p>
<ul>
  <li>URL: Jenkins URL</li>
  <li>USER: Jenkins username</li>
  <li>TOKEN: Jenkins dashboard → profile → configure → API token → add new Token → Generate → copy the Token</li>
  <li>JOB: job created in Jenkins: pipeline</li>
</ul>

<p>Now we can push the code into GitHub. GitHub repo will trigger the Jenkins Server. Manually Trigger the pipeline/workflow:</p>
<ul>
  <li>GitHub → actions → Trigger Jenkins Job → Run workflow → run workflow → workflow starts → and triggered the Jenkins server → Build has started in Jenkins Server → Build the images and push the image into ECR and execute the application</li>
</ul>
