# Bayes Classifier on GCP Dataproc

Please follow these steps.

### Create Dataproc cluster
In CloudShell:
* Clone the repository if you haven't already done so:
    ```
    git clone https://github.com/hung2xt/gcp-dataproc.git
    ```
* Create the Dataproc cluster to run jobs on, specifying the name of your bucket and a 
  zone in the region that the bucket is in. (You created this bucket in Chapter 2)
   ```
    ./create_cluster.sh <BUCKET-NAME><COMPUTE-ZONE>
    ```
*Note:* Make sure that the compute zone is in the same region as the bucket, otherwise you will incur network egress charges.

### Interactive development
* Navigate to the Dataproc section of the GCP web console and click on "Web Interfaces".

* Click on JupyterLab on the folders examples

* Open quantization.ipynb. Click Run | Clear All Outputs. Then run the cells one by one.
 
* [optional] make the changes suggested in the notebook to run on the full dataset.  Note that you might have to
  reduce numbers to fit into your quota.
  
### Delete the cluster
* Delete the cluster either from the GCP web console or by typing in CloudShell, ```./delete_cluster.sh <YOUR REGION>```

### Serverless workflow
* Visit https://console.cloud.google.com/networking/networks/list
* Select the "default" network in your region and allow private Google access
* Run ./submit_serverless.sh
 
