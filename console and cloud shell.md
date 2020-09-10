# LAB: Console and Cloud Shell

## OBJECTIVES:
		*Get access to Google Cloud.
		*Create a Cloud Storage bucket using the Cloud Console.
		*Create a Cloud Storage bucket using Cloud Shell.
		*Become familiar with Cloud Shell features.

## STEPS
		
	1.  i.Create a  bucket	("Globally unique Name") :
			gsutil mb gs://<BUCKET_NAME>
		ii. Create a  bucket	("Globally unique Name") :
			gsutil mb gs://<BUCKET_NAME>
	
	2. Explore more Cloud Shell features	
	 --Upload a file:
		-Click the three dots in the Cloud Shell toolbar to display further options./
		Click Upload file. Upload any file from your local machine to the Cloud Shell VM. This file will be referred to as [MY_FILE].
	 
	 -- To confirm that the file was uploaded:
		ls 
	 
	 --Copy the file into the buckets you created. Replace [MY_FILE] with the file you uploaded and [BUCKET_NAME] with theone of your bucket name:
		gsutil cp [MY_FILE] gs://[BUCKET_NAME]
		Result:You have uploaded a file to the Cloud Shell VM and copied it to a bucket.
		
	3. Become familiar with Cloud Shell features. (Create a persistent state in Cloud Shell)
	 --list available regions
		gcloud compute regions list
		
	 --Select a region from the list and note the value in any text editor. This region will now be referred to as [YOUR_REGION] in the remainder of the lab.	
	
	 --Create and verify an environment variable
		INFRACLASS_REGION=[YOUR_REGION] --echo $INFRACLASS_REGION
		
	 --Append the environment variable to a file:
		mkdir infraclass 
	 
	 --Create a file called config in the infraclass directory:
		touch infraclass/config 
	 
	 --Append the value of your Region environment variable to the config file:
		echo INFRACLASS_REGION=$INFRACLASS_REGION >> ~/infraclass/config
		
	 --Create a second environment variable for your Project ID:
		INFRACLASS_PROJECT_ID=[YOUR_PROJECT_ID]
		
	 --Append the value of your Project ID environment variable to the config file:
		echo INFRACLASS_PROJECT_ID=$INFRACLASS_PROJECT_ID >> ~/infraclass/config
	 
	 --Use the source command to Set the environment variables, and use the echo command to verify that the project variable was set:	
	 
	 --Close and re-open Cloud Shell. Then issue the echo command again:
		echo $INFRACLASS_PROJECT_ID
		Result:There will be no output because the environment variable no longer exists.
		
	 --Modify the bash profile and create persistence:
		nano .profile 
		--Add the following line to the end of the file:
			source infraclass/config
		
	   Press Ctrl+O, ENTER to save the file, and then press Ctrl+X to exit nano.
	 --Close and re-open Cloud Shell. To verify that the variableis still set:
		echo $INFRACLASS_PROJECT_ID
		Result:You should now see the expected value that you set in the config file.
		
## End of LAB
	
		
		
		
		
		
		
		
		
		































