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
 
 ---
 
 ## Create Custom Connector
 Now open Power Apps, (http://make.powerapps.com/)[http://make.powerapps.com/] and click on Create -> "Canvas app from blank"
  ![image](30-PPCreateApp.jpg)
 
 Enter an App name and click on Create
 ![image](31-PPEnterAppName.jpg)
 
 In the Apps Cancas click on the Data icon on the right, click on "Add data" Search for the Customer Connector name you previously created and select it. 
 ![image](32-PPAppsCanvas.jpg)
 
 As a result you should see the new data source "Search Help"
 ![image](33-DataAdded.jpg)
 
 Now click on Insert and Drag and drop a Text Input and Button onto the canvas
 ![image](34-DragElements.jpg)
 
 Search for Table, select the Data table (preview) and drag it onto the canvas as well. 
 ![image](35-insertTable.jpg)
 
 Now select the button you created. Make sure that the Action for the Button is OnSelect and enter the formula, 

>>>> ClearCollect(Customers, 'SearchHelp:SH(Searchhelp)|DEBIA-Customers(general)'.POSTexecute(800,{MAXROWS:100, MCOD1:Table({SIGN: "I",OPTION: "CP",LOW: Concatenate("*",TextInput1.Text,"*"),HIGH: ""})}).result.DATA);

  ![image](36-ClearCollect.jpg)
 
 Note: 
 * ClearCollect creates a new collection that we can easily poulate and use in other items. 
 * SearchHelp:SH is the Custom Connection that we created in step xxx. 
 * The POSTexecute step is the function to lookup the customer information 
 * it requires several mandatory parameters, like SAP-Client (800), MAXROWS (a default value of 100 as an example), MCOD1 (a Table with information on what customer information we should look for)
 * TextInput1.Text is the value the user interes in the Input Field. You can find the exect propertyname by clicking on the Next infput field
 
 ![image](37-TextInputField.jpg)
 
 Now click on the table and link newly created Collection "Customers" to it. 
 ![image](38-LinkTable.jpg)
 
 On the right hand side under Data sources -> Customers click on Fields -> Edit fields, click on "+ Add field" and select the two properties KUNNR and MCOD1. Then click on Add. 
 ![image](39-ChooseFields.jpg)
 
 The result should look like this (now you can see the name of the two columns). It's time to test the Power Apps. On the upper right corner click on the "Play" button. 
 ![image](40-ColumnNames.jpg)
 
 Enter some letters in the Input field and click the button. As a result you should see customer data displayed in the Power App. 
 ![image](41-TryitOut).jpg
 
 
 
 
 

 
 

  
  
