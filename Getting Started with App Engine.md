# LAB:Google Cloud Fundamentals: Getting Started with App Engine

## OBJECTIVES:
	*Initialize App Engine.
	*Preview an App Engine application running locally in Cloud Shell.
	*Deploy an App Engine application, so that others can reach it.
	*Disable an App Engine application, when you no longer want it to be visible.
	
## STEPS
	1.Initialize App Engine
	 --Set Project Core:
		gcloud config set project [PROJECT_ID]
	 
	 --Initialize App Engine:
		gcloud app create --project=$DEVSHELL_PROJECT_ID
		"When prompted, select the region where you want your App Engine application located."
	 
	 --Clone the source code repository for a sample application in the hello_world directory:
		git clone https://github.com/GoogleCloudPlatform/python-docs-samples
	 
	 --Navigate to the source directory:
		cd python-docs-samples/appengine/standard_python3/hello_world
	
	2. Preview an App Engine application running locally in Cloud Shell.
	 --download and update the packages list:
		sudo apt-get update
	 
	 --Set up a virtual environment in which you will run your application:
		sudo apt-get install virtualenv "If prompted [Y/n], press Y and then Enter." --virtualenv -p python3 venv
	 
	 --Activate the virtual environment:	
		source venv/bin/activate
	 
	 --Navigate to your project directory and install dependencies:
		pip install  -r requirements.txt
	 
	 --Run the application: 
		python main.py
	 
	 --click Web preview (Web Preview) > Preview on port 8080 to preview the application.
	 Result: Hello World!
	
	3. Deploy and run Hello World on App Engine 
	 --To deploy your application to the App Engine Standard environment Navigate to the source directory:
		cd ~/python-docs-samples/appengine/standard_python3/hello_world 
	 
	 --Deploy your Hello World application
		gcloud app deploy "if prompted "Do you want to continue (Y/n)?", press Y and then Enter."
	 
	 --To view the app
		gcloud app browse "Copy and paste the URL into a new browser window"
		Result:Hello World
		
	4. Disable an App Engine application
	 --("After disabling the application If you refresh the browser window you used to view to the application site, you'll get a 404 error.")
	 
## End of LAB
	
	
	
	
	
	
	
	
	
	
	
	


	 
	 
	 
	 
	 
	 
	 
	 
	 
		
		
		
		
		













