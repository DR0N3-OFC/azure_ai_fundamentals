<h1 style="text-align: center;">Module 01 - Automated Machine Learning 🧠</h1>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">In the first module of the bootcamp, we were introduced to an new environment called Azure Machine Learning, on which we can use Machine Learning Models for any purpose.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">At this lab, we passed through every step of creating Workspaces, choosing the ML models we wanna use and more. So stay tunned and follow me on this step-by-step I made specially for you to learn how to implement your first AI solution on Azure Machine Learning Environment. 🚀</p>

<h2 style="padding-left: 15px; padding-right: 15px;">Creating an Workspace</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <a href="https://ml.azure.com/">Standart Directory</a> page, create a new workspace by clicking on the <b>Create workspace button</b> or enter in an existing workspace.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Workspaces.png" alt="Defining the workspace" />


<h2 style="padding-left: 15px; padding-right: 15px;">Inside the workspace</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Inside the workspace page you'll see the following screen.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">In that page you can see a lot of Machine Learning models ready to use.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Inside the Workspace.png" alt="Inside the workspace" />

<h2 style="padding-left: 15px; padding-right: 15px;">Creating an Automated ML job</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <b>Authoring</b> menu section, on the <b>Automated ML tab</b>, click on the <b>New Automated ML job button</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Automated ML.png" alt="Automated ML" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <b>Training Method</b> section click on <b>Start configuring job</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Training Method.png" alt="Training Method" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <b>Basic settings</b> section, define the <b>job name</b>, <b>Experiment name</b> and click on <b>Next</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Basic Settings.png" alt="Basic Settings" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On <b>Task type</b> select the <b>Regression</b> option and, in the <b>Select data</b> section click on <b>Create</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Task Type and Data.png" alt="Task Type and Data" />

<h3 style="padding-left: 15px; padding-right: 15px;">Creating the Data Asset</h3>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">After clicking on the <b>Create</b> button, you'll see the following page. On that, define the asset's <b>Name</b>, <b>Description</b> and the <b>Type</b> of the data asset.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Click <b>Next</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Create Data Asset.png" alt="Create Data Asset" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Choose the asset's data source, in this case, <b>From web files</b> and click on <b>Next</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Data Source.png" alt="Data Source" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Paste, on the <b>Web URL textbox</b>, the <b>data source URL</b> and click on <b>Next</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Web URL.png" alt="Web URL" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <b>Settings</b> page, define the <b>File format</b>, <b>Delimiter</b> the <b>Coding</b> of the data and the <b>Collumn headers</b>, in this case, <b>Only first file has headers</b> defines that the headers will be shown only once in the first row of the first page.You can see the formatted data on the <b>Data preview table</b>.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">After finishing click on <b>Next</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Settings.png" alt="Data Asset Settings" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Review the Schema and choose the columns to be used on the learning job. But leave the <b>Path</b> column unchecked, because it's just the data source host path and is not used for learning purposes.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;"><i>* Check if the data types are correctly selected.</i></p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Schema.png" alt="Data Schema" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Review the result of Data Asset and click <b>Create</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Review.png" alt="Review Data Asset" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Select the created Data Asset and click <b>Next</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Successfully Added.png" alt="Data Asset Successfully Added" />

<h3 style="padding-left: 15px; padding-right: 15px;">Task Settings</h3>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Now, let's define the task settings for this machine learning job.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">First of all, on the <b>Target column</b> select the <b><i>rentals (Integer)</i></b> column and click on <b><i>View additional configuration settings</i></b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Task Settings.png" alt="Task Settings" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">As the <b>Primary metric</b> select the <b><i>NormalizedRootSquaredError</i></b> as error metric, uncheck all the checkboxes and select <b><i>RandomForest</i></b> and <b><i>LightGBM</i></b> models.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Click on <b>Save</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Additional Configuration Settings.png" alt="Additional Configuration Settings" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Still on the <b>Task settings</b> page, go to the <b>Limits</b> section and replicate the informations on the image below.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">This informations refer to the <b>trial number</b>, <b>acceptable error score</b>, etc.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Limits.png" alt="Limit metrics" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">below on the <b>Task settings</b> page, go to the <b>Validate and test</b> section and replicate the informations on the image below.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">This informations refer to the <b>type of validation</b>, <b>percentage of the data split for validation of results</b> and <b>test data</b>.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Click <b>Next</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Validation and Test.png" alt="Validation and Test" />

<h3 style="padding-left: 15px; padding-right: 15px;">Compute</h3>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">The <b>compute</b> section is where you can choose the <b>compute type</b> and <b>hardware</b> where your Machine Learning job will be executed.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">The virtual machine size selected is the standart. If you select an more robust machine, the cost will be elevated, leading you to waste your credits quickly, but the machine learning jobs will be executed quickly too.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Replicated the following informations, click <b>Next</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Compute.png" alt="Compute" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Review the <b>Automated ML job</b> informations and click <b>Submit training job</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Review Informations.png" alt="Review Automated ML job informations" />

<h2 style="padding-left: 15px; padding-right: 15px;">Running Automated ML Job</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Now, the created ML job is running. You can follow the progress of the job at the page below.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Running.png" alt="Running Automated ML job" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">After the completion, the status of the ML job will become <b>Completed</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Completed.png" alt="Completed Automated ML job" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <b>Metrics</b> tab, you can see all the metrics obtained by the job execution.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">The <b>Normalized Mean Squared Error</b> achieved the especified metrics at the job creation and the <b>Predicted values</b> were satisfactory.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Metrics.png" alt="Metrics from the Automated ML job" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">For testing the model with new values, go to the <b>Overview</b> tab, and click on Deploy as a Web Service.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Replicate all the informations and click on <b>Deploy</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Deploy.png" alt="Deploy of the ML model" />

<h2 style="padding-left: 15px; padding-right: 15px;">Testing the Model</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Finally, go to the <b>Endpoints</b> sections and select the deployed model.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Click on <b>Test</b> and paste an <b>JSON content</b> at the <b>Input data</b> textbox.
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Click <b>Test</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 01 - Automated Machine Learning/Deploy Test.png" alt="Deploy test of the ML model" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">The result was shown and our model is working.</p>