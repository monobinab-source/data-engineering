Setting Up Python for Google Cloud:

In order to work from command line and connect to Google Cloud from CLI we have to set Up Google Cloud SDK:
pip install google-cloud-storage
Set up a GCP Console project.
gcloud init #by this you select your project and region and connect to it.


Create Service account if you are scheduling jobs. Google prefers that you access the resources through service account rather than individual account:
gcloud iam service-accounts create <service account name>
gcloud projects add-iam-policy-binding <service account name> --member "<service account name>@<projectid>.iam.gserviceaccount.com" --role "roles/owner"
gcloud iam service-accounts keys create ../.json --iam-account <service account name>@<projectid>.iam.gserviceaccount.com

export GOOGLE_APPLICATION_CREDENTIALS=<path where the service account key is stored>
export GOOGLE_APPLICATION_CREDENTIALS=<service account key file with path>

To work with cloud resource manager and google APIs: 
pip install google-cloud-resource-manager 
pip install google-api-python-client
pip install httplib2
pip install oauth2client
pip install --upgrade google-api-python-client
pip install --upgrade google-cloud-bigquery


Enable Cloud Resource Manager API by going to the console and 
1. click on API and Services
2. Click on the : +Enable APIs and Services , on the right of the API and Services
3. This will lead to Welcome to API Library
4. Search for "Cloud Resource Manager", click on it and then it will take to the Cloud Resource Manager API page and "Enable API" there. This needs to be done for python program to get Google Cloud authorization.


If you are using google spreadsheet to input file
pip install gspread oauth2client

Also share your spreadsheet with service account email address, which can be found in key file that you download from console.