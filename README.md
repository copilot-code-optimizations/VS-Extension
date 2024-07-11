# Code Optimizations extension (preview) for Visual Studio 

1. [PREREQUISITES](#Prerequisites)
2. [INSTALLATION](#Installation)
3. [USAGE](#Usage)

<a name="Prerequisites"></a>
# Prerequisites 
## GitHub Account
For the extension to work - you need to have a Github Copilot subscription.

## Application Insights Code Optimizations
1. Make sure Azure Application Insights and Application Insights Profiler are enabled for your .NET apps. If not, please follow these instructions [Application Insights](https://learn.microsoft.com/en-us/azure/azure-monitor/app/create-workspace-resource?tabs=bicep) and [Application Insights Profiler](https://learn.microsoft.com/en-us/azure/azure-monitor/profiler/profiler) to enable them.
2. Validate that Code Optimizations are identified for your application - go into the **Performance** blade of your Application Insights resource and click on “**Code Optimizations**” as shown below
<img src="IMAGES/CodeOptimizations1.png" width="600" />

4. Please note down (a) the Application Insights resource name, (b) the account that you are using to sign into Azure portal.

## Visual Studio and GitHub Copilot Chat
1.	Current versions of extensions were tested with Visual Studio 17.9, 17.10 and 17.11. If you are using a different version of Visual Studio and the extension is not working, please let us know
2.	Open Visual Studio and ensure you are signed in with both - your GitHub account and the account that you used to access Azure portal. You can validate on the top right corner of Visual Studio. If one account is missing, add it. Without both accounts added, the current version of the Code Optimizations extension will not work correctly. 
<img src="IMAGES/Accounts1.png" width="200" />

3. Open GitHub Copilot chat using menu command **View -> GitHub Copilot Chat**. If it's not available and you are using Visual Studio 17.9 or older, please make sure you have installed the GitHub Copilot Chat extension using **Extensions -> Manage Extensions...**

# Add Code Optimizations (preview) feed into the extensions gallery 
1. Launch Visual Studio
3. Open Options dialog using **Tools-> Options...** command, then select **Extensions**
4. Add a new feed named "Code Optimizations" with the URL "https://salmon-coast-03fbc8d1e.5.azurestaticapps.net/feed.xml"
<img src="IMAGES/Installation2.png" width="600" />
   
5. Click **Apply** and **OK** to close the Options dialog.

<a name="Installation"></a>

# Install the Code Optimizations (preview) extension


**NOTE**
If you have upgraded your Visual Studio 17.9 with Code Optimizations extension to Visial Studio 17.10 or 17.11, please un-install the Code Optimizations extension and install the extension intended for 17.10 and 17.11. It's available in the same feed in your Visual Studio. Why? The GitHub Copilot Chat is built into VS 17.10+ and the architecture has changed a bit, so a different extension version is necessary. The chat experience remains un-changed.


1. Now we can install the extension from the **Extensions -> Manage Extensions...**
2. Find the Code Optimizations category under **Visual Studio Marketplace** 
<img src="IMAGES/Installation3.png" width="600" />

4. If you are using the New Extension Manager "UI Refresh" you will find the category in ... -> Browsing Location -> Code Optimizations
<img src="IMAGES/Installation4.png" width="600" />
   
6. Install the version that matches your Visual Studio version
7. Yes, you need to close the Visual Studio for the installation to start. Please pay attention to the installation dialog, your consent maybe neccesary
8. Once installation completes, please start Visual Studio
   
# Usage 

### Visual Studio Extension

1. Open VS
2. Open the repo for the app you have insights for in Code Optimizations
3. Open GitHub Copilot Chat
4. The Code Optimizations (preview) extension introduces an "agent" called `@code_optimizations` with a few commands or *skills* that let you interface with Code Optimizations issues. To invoke the extension,  type `@code_optimizations` followed by the skill and the necessary parameters:

#### @code_optimizations /connect <Application_Insights_Resource_Name>

where <Application_Insights_Resource_Name> is the name of the Appliation Insights. The command will pull the top issues from Code Optimizations, map them to source code in your local repo and try suggesting fixes / recommendations. It will automatically generate the first fix it's able to offer. To generate fixes for other issues, follow the instructions in the Copilot response.

<img src="IMAGES/CodeOptimizations2.png" width="800" />

# Feedback
Your feedback is important to us! If you have any questions or suggestions, please reach out to our email alias: codeoptimizations@microsoft.com or open an issue in this repo.

Thank you! ❤️

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
