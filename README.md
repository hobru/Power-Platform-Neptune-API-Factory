# Power-Platform-Neptune-API-Factory

## Sign up to the Netpune Developer Trial
Go to https://www.neptune-software.com/free-trial/ scroll down and click on "Download Free Trial"

Click on Register

and fill in the required information. Select "Neptune DXP SAP edition [Planet 8]" and click on Register

You should get an Email with the required information to sign in to the Netpune Software Account Portal. We will log onto the portal later on in step xx

## Sign up to the Power Platform Developer Trial
Go to https://powerapps.microsoft.com/en-us/developerplan/ and sign up for the "Power Apps Developer Plan"

Fill in the required information. 

Note: If you have problems signing in with your work / school account, go to https://developer.microsoft.com/en-us/microsoft-365/dev-program and sign up for the Microsoft 365 Developer Program first. 



With this we can switch over to the Power Platform, (https://us.flow.microsoft.com/en-us/)[https://us.flow.microsoft.com/en-us/]. 

Under Data -> Customer Connectors click on "+ New custom connector" and select "Import an OpenAPI from URL". 

Enter the URL from the Swagger.ui, e.g. https://demo-sap-apim.azure-api.net/neptune/api/dynamic/neptune/cl_dr_lib_ddic_shlp_x/SH/DEBIA/swagger.json?oas_version=2.0&sap-user=<user>&sap-password=<password>
 Make sure to replace the <user> and <password> with the username and password of your SAP system (alternatively you can also download and upload the Swagger file)
  
and click on Import -> Continue
  
 
Now double check the configuration. Click on Security,
  
Definition
  
  
