
# **CHEST DISEASE CLASSIFICATION USING CT-SCAN**

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




<h2>Mlflow  Experiment Tracking : </h2>

Example :

ElasticNet : parameters (alpha , L1 ) 
                    0.7 , 0.9  exp 1 70%
                    0.5 , 0.5  exp 280%
                    0.4 , 0.6  exp 350%
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
