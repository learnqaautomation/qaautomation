# qaautomation

**Steps to be followed for starting Selenium Grid using Zalenium and running our automation suite:**

1) Install docker from https://www.docker.com/products/docker-desktop
2) Place the Zalenium Script in the root directory of the automation suite
3) Execute the bashscript (./ZaleniumSetup.sh) that is located in the root directory of our Web Automation suite.
4) Give root privilege to the script by giving chmod 777 ZaleniumSetup.sh
5) Below are the options available within script,

   **a) To get Insight on the Parameters that is required for executing the script,**

       ./ZaleniumSetup.sh -h 
      
      ![image](https://user-images.githubusercontent.com/83286077/116243141-3e704980-a784-11eb-8a77-076110e2d70c.png)

 
   **b) To execute the script,**
   
       ./ZaleniumSetup.sh <desiredContainers> <maxDockerSeleniumContainers> <videoRecordingEnabled>
   
      Example:
      
       ./ZaleniumSetup.sh 3 3 true
      
      Above command will start Selenium Grid with 3 containers with video recording enabled
   
   **c) To Stop the Zalenium server,**
   
       ./ZaleniumSetup.sh -s
    
 6) Once the above steps are done, we need to point our tests to http://localhost:4444/wd/hub in our automation framework. This URL should be set as the argument to     RemoteWebDriver along with DesiredCapabilities.
 
      **Sample Code Snippet:**
    
	![image](https://user-images.githubusercontent.com/83286077/116246310-7f1d9200-a787-11eb-93d7-75b9d6715805.png)
			
 7) Execute the automation suite using the appropriate mvn command
 8) Once the automation suite is execuetd, below URLs to will help us to view and track execution status,
 
    **a) Grid Console:**
    
        http://localhost:4444/grid/console
	
	ZaleniumGridConsole.png![image](https://user-images.githubusercontent.com/83286077/116290458-19460000-a7b1-11eb-8bd3-5fdc243ba8fe.png)

     
    **b) Grid Execution console:**
    
        http://localhost:4444/grid/admin/live?refresh=10
      
       where refresh value can be altered as per our need in the above URL
      
       ZaleniumGrid.png![image](https://user-images.githubusercontent.com/83286077/116290476-1d721d80-a7b1-11eb-9767-399c3e49f414.png)

      
    **c) Test execution dashboard which will contain all our recorded tests:**
    
         http://localhost:4444/dashboard/
	
	 ZaleniumDashboard.png![image](https://user-images.githubusercontent.com/83286077/116290499-24009500-a7b1-11eb-948c-2116ee4b3483.png)

   
   

