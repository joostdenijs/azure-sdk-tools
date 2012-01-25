<h1>Windows Azure PowerShell for Node.js</h1>
<p>This repo contains a set of PowerShell commandlets that let you deploy Node.js
application to Windows Azure from the command line. For documentation on how
to host Node.js applications on Windows Azure, please see the
<a href="http://www.windowsazure.com/en-us/develop/nodejs/">Windows Azure
Node.js Developer Center</a>.</p>

<h1>Features</h1>
<p>Configure machines for publishing to the cloud.</p>
<ul>
    <li><strong>Get-AzurePublishSettings</strong> - Downloads a Windows Azure publish profile
    to your local computer </li>
    <li><strong>Import-AzurePublishSettings</strong> - Imports the Publish Profile to enable
    publishing to Azure and managing hosted services</li>
</ul>
<p>Create services and roles that are preconfigured to use Node.js.</p>
<ul>
    <li><strong>New-AzureService</strong> - Creates scaffolding for a new service</li>
    <li><strong>Add-AzureNodeWebRole</strong> - Creates scaffolding for a Node.js application
    which will be hosted in the cloud via IIS</li>
    <li><strong>Add-AzureNodeWorkerRole</strong> - Creates scaffolding for a Node.js application
    which will be hosted in the cloud via node.exe</li>
</ul>
<p>Debug your applications in the local compute and storage emulators</p>
<ul>
    <li><strong>Start-AzureEmulator</strong> - Starts both the compute and storage emulators
    and executes the service</li>
    <li><strong>Stop-AzureEmulator</strong> - Stops the compute emulator</li>
</ul>
<p>Publish your service to the cloud and configure publish settings</p>
<ul>
    <li><strong>Publish-AzureService</strong> - Publish the current service to the cloud</li>
    <li><strong>Set-AzureDeploymentStorage</strong> - Sets the storage account to be used when
    publishing the service to the cloud</li>
    <li><strong>Set-AzureDeploymentSubscription</strong> - Sets the subscription name to be
    used when publishing the service to the cloud</li>
    <li><strong>Set-AzureDeploymentLocation</strong> - Sets the deployment location for the
    current service</li>
    <li><strong>Set-AzureDeploymentSlot</strong> - Sets the deployment slot for the current
    service</li>
    <li><strong>Set-AzureInstances</strong> - Set the number of instances for the specified role</li>
</ul>
<p>Manage your hosted services</p>
<ul>
    <li><strong>Start-AzureService</strong> - Starts the current hosted service</li>
    <li><strong>Stop-AzureService</strong> - Stops the current hosted service</li>
    <li><strong>Remove-AzureService</strong> - Removes the current hosted service</li>
    <li><strong>Get-AzureStorageAccounts</strong> - Retrieves and displays storage account
    details for the specified Azure subscription.  If no subscription is
    specified, uses the first subscription in your Azure publish profile</li>
    <li><strong>Enable-AzureRemoteDesktop</strong> - Enables remote desktop access to a hosted service</li>
    <li><strong>Disable-AzureRemoteDesktop</strong> - Disables remote desktop access to a hosted service</li>
</ul>

<h1>Getting Started</h1>
<h2>Download Source Code</h2>
<p>To get the source code of the SDK via git just type:<br/>
<pre>git clone https://github.com/WindowsAzure/azure-sdk-tools.git<br/>cd ./azure-sdk-tools</pre>
</p>
<h2>Install Prerequisites</h2>
<ul>
    <li><a href="http://nodejs.org/">Node.js</a></li>
    <li><a href="https://github.com/tjanczuk/iisnode">IISNode</a></li>
    <li><a href="http://www.microsoft.com/windowsazure/sdk/">Windows Azure SDK</a></li>
    <li><a href="http://technet.microsoft.com/en-us/scriptcenter/dd742419">Windows PowerShell 2.0</a></li>
    <li><a href="http://wix.sourceforge.net/">WiX</a> (Only needed if you want to build the setup project)</li>
</ul>
<h2>Configure PowerShell to automatically load commandlets</h2>
<ol>
    <li>Create a folder inside your user's Documents folder and name it <strong>WindowsPowerShell</strong></li>
    <li>Inside that folder create a file called <strong>Microsoft.PowerShell_profile.ps1</strong></li>
    <li>Edit the file in a text editor and add the following contents<br/>
    <pre>Import-Module<br/>PATH_TO_AZURE-SDK-TOOLS_CLONE\AzureDeploymentCmdlets\src\AzureDeploymentCmdlets\bin\Debug\AzureDeploymentCmdlets.dll</pre></li>
    <li>After you build the commandlets project, you can then open a PowerShell window and you should be able to use the commandlets. Please note that if you want to rebuild the project, you have close the PowerShell window, and then reopen it.</li>
</ol>

<h1>Usage</h1>
<ol>
    <li>First, create an Azure hosted service called HelloWorld by typing<br/>
    <pre>New-AzureService HelloWorld</pre></li>
    <li>Inside the HelloWorld folder, add a new Web Role by typing<br/>
    <pre>Add-AzureNodeWebRole</pre></li>
    <li>Test out the application in the local emulator by typing<br/>
    <pre>Start-AzureEmulator -Launch</pre></li>
    <li>You are now ready to publish to the cloud service. Go ahead and register
    for a Windows Azure account and make sure you have your credentials handy.</li>
    <li>Get your account's publish settings and save them to a file<br/>
    <pre>Get-AzurePublishSettings</pre></li>
    <li>Now import the settings<br/>
    <pre>Import-AzurePublishSettings PATH_TO_PUBLISH_SETTINGS_FILE</pre></li>
    <li>You are now ready to publish to the cloud. Make sure you specify a
    unique name for your application to ensure there aren't any conflicts during
    the publish process<br/>
    <pre>Publish-AzureService -Name UNIQUE_NAME -Launch</pre></li>
</ol>

<h1>Need Help?</h1>
<p>Be sure to check out the Windows Azure <a href="http://go.microsoft.com/fwlink/?LinkId=234489">
Developer Forums on Stack Overflow</a> if you have trouble with the provided code.</p>

<h1>Contribute Code or Provide Feedback</h1>
<p>If you would like to become an active contributor to this project please follow the instructions provided in <a href="http://windowsazure.github.com/guidelines.html">Windows Azure Projects Contribution Guidelines</a>.</p>
<p>If you encounter any bugs with the library please file an issue in the <a href="https://github.com/WindowsAzure/azure-sdk-tools/issues">Issues</a> section of the project.</p>


<h1>Learn More</h1>
<ul>
    <li><a href="http://www.windowsazure.com/en-us/develop/nodejs/">Windows Azure Node.js
    Developer Center</a></li>
</ul>
