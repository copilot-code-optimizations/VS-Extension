# Code Optimizations extension (preview) for Visual Studio 

1. [PREREQUISITES](#Prerequisites)
2. [INSTALLATION](#Installation)
3. [USAGE](#Usage)

<a name="Prerequisites"></a>
# 1. Prerequisites 
## 1.1. Your GitHub Account Settings


1.1.1. Please make sure your GitHub account has a valid Github Copilot subscription.


1.1.2. Your GitHub account needs to be part of this organization "copilot-code-optimizations" to enable you access this preview feature. If you have not done already, please fill in this form https://aka.ms/CodeOptimizations/PreviewFeatures, our team will send you the invitation.


1.1.3. Once you accept the invitation to join this organization, please change your membership from Private to Public on settings page https://github.com/orgs/copilot-code-optimizations/people.


## 1.2. Validate your Application Insights Code Optimizations
1.2.1. Make sure Azure Application Insights and Application Insights Profiler are enabled for your .NET apps. If not, please follow these instructions [Application Insights](https://learn.microsoft.com/en-us/azure/azure-monitor/app/create-workspace-resource?tabs=bicep) and [Application Insights Profiler](https://learn.microsoft.com/en-us/azure/azure-monitor/profiler/profiler) to enable them.


1.2.2. Validate that Code Optimizations are identified for your application - go into the **Performance** blade of your Application Insights resource and click on “**Code Optimizations**” as shown below
<img src="IMAGES/CodeOptimizations1.png" width="600" />


1.2.3. Please note down (a) the Application Insights resource name, (b) the account that you are using to sign into Azure portal. You will need to use both later.


## 1.3. Configure GitHub Copilot Chat in Visual Studio  


1.3.1.	Current versions of extensions were tested with Visual Studio 17.9, 17.10 and 17.11. If you are using a different version of Visual Studio and the extension is not working, please let us know.


1.3.2.	Open Visual Studio and ensure you are signed in with both - your GitHub account and the account that you used to access Azure portal. You can validate on the top right corner of Visual Studio. If one account is missing, add it. Without both accounts added, the current version of the Code Optimizations extension will not work correctly. 
<img src="IMAGES/Accounts1.png" width="200" />


1.3.3. Open GitHub Copilot chat using menu command **View -> GitHub Copilot Chat**. If it's not available and you are using Visual Studio 17.9 or older, please make sure you have installed the GitHub Copilot Chat extension using **Extensions -> Manage Extensions...**.


# 1.4. Add Code Optimizations (preview) feed into the extensions gallery 


1.4.1. Launch Visual Studio


1.4.2. Open Options dialog using **Tools-> Options...** command, then select **Extensions**


1.4.3. Add a new feed named "Code Optimizations" with the URL "https://salmon-coast-03fbc8d1e.5.azurestaticapps.net/feed.xml".
<img src="IMAGES/Installation2.png" width="600" />


1.4.4. Click **Apply** and **OK** to close the Options dialog.

<a name="Installation"></a>

# 2.1. Install the Code Optimizations (preview) extension


> [!IMPORTANT] 
If you upgrade your Visual Studio 17.9 with Code Optimizations extension to Visual Studio 17.10 or 17.11, please un-install the Code Optimizations extension and install the extension intended for 17.10 and 17.11. It's available in the same extension feed. Why? The GitHub Copilot Chat is built into VS 17.10+ and the architecture has changed a bit, so a different extension version is necessary. The chat experience remains un-changed.

2.1.1 Now we can install the extension from the **Extensions -> Manage Extensions...**


2.1.2. Find the Code Optimizations category under **Visual Studio Marketplace** 
<img src="IMAGES/Installation3.png" width="600" />

2.1.3. If you are using the New Extension Manager "UI Refresh" you will find the category in ... -> Browsing Location -> Code Optimizations
<img src="IMAGES/Installation4.png" width="600" />
   
2.1.4. Install the version that matches your Visual Studio version


2.1.5. Yes, you need to close the Visual Studio for the installation to start. Please pay attention to the installation dialog, your consent maybe neccesary


2.1.6. Once installation completes, please start Visual Studio
   
# 3. Usage 

### Visual Studio Extension

3.1.1. Open VS\

3.1.2. Open the repo for the app you have insights for in Code Optimizations\

3.1.3. Open GitHub Copilot Chat\

3.1.4. The Code Optimizations (preview) extension introduces an "agent" called `@code_optimizations` with a few commands or *skills* that let you interface with Code Optimizations issues. To invoke the extension,  type `@code_optimizations` followed by the skill and the necessary parameters:

#### @code_optimizations /connect <Application_Insights_Resource_Name>

where <Application_Insights_Resource_Name> is the name of the Application Insights resource. The command will pull the top issues from Code Optimizations, map them to source code in your local repo and try suggesting fixes / recommendations. It will automatically generate the first fix it's able to offer. To generate fixes for other issues, follow the instructions in the Copilot response.

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
