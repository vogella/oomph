

Eclipse Platform SDK Provisioning
=================================

[![Oomph Project Logo.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Project_Logo.png)](/Oomph "Oomph")[Powered by Oomph](/Oomph "Oomph")

This page provides step-by-step instructions for how to provision a dedicated development environment for the complete set of projects that comprise the [Eclipse Platform's SDK](/Eclipse_Project "Eclipse Project"), i.e., the projects used to build the [downloads](http://download.eclipse.org/eclipse/downloads/) of the Eclipse Platform Project. The provisioning process is entirely automated, except for course from user input to choose configurable options, e.g., where in the file system to place the installation, but even for these, defaults are provided.

If you encounter problems or have suggestions for improvements, please use [Bug 536533](https://bugs.eclipse.org/bugs/show_bug.cgi?id=536533) for that purpose.

Contents
--------

*   [1 Launch the Eclipse Installer](#Launch-the-Eclipse-Installer)
*   [2 Apply the Platform SDK Configuration](#Apply-the-Platform-SDK-Configuration)
*   [3 Review the Variables](#Review-the-Variables)
*   [4 Confirm the Tasks](#Confirm-the-Tasks)
*   [5 Monitor the Progress](#Monitor-the-Progress)
*   [6 Provision the Workspace](#Provision-the-Workspace)
*   [7 Review the Result](#Review-the-Result)
*   [8 Update the Installation and Workspace](#Update-the-Installation-and-Workspace)

Launch the Eclipse Installer
----------------------------

If you don't already have the [Eclipse Installer](Eclipse_Installer.md "Eclipse Installer") on your system, [download](Eclipse_Installer.md "Eclipse Installer") the installer that is appropriate for your operating system's architecture. For Windows, the installer is distributed as an executable. It will start without a JRE or JDK installed, but if you don't have at Java 8 installed, it will guide you to install that. For Mac and Linux, you must unpack the installer before you can run the application. In all cases, you must install a JRE or JDK (currently at least Java 8) before you can successfully use the installer, and of course the installation you will create needs it too. Please look at [these instructions](/Eclipse/Installation#Install_a_JVM "Eclipse/Installation") if you need further details. And note that on Mac you must install a JDK, not merely a JRE.

The latest version if the installer can be registered to automatically launch when clicking on a hyperlink. This can be used to further automate the initial steps in this tutorial. As such, you can open [this link](https://www.eclipse.org/setups/installer/?url=https://raw.githubusercontent.com/eclipse-platform/eclipse.platform.releng.aggregator/master/oomph/PlatformSDKConfiguration.setup&show=true) in a new tab to configure the installer to launch automatically.

Now launch the installer application. Unless you just downloaded a new installer, the one you have probably needs to be updated. In simple mode, you'll see a "!" indicator on the menu button in the upper right corner; the menu will have an update item to start an update:

![Oomph Installer Simple Update.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Installer_Simple_Update.png)

In advanced mode, the right-most toolbar button at the bottom can be pressed to start an update.

![Oomph Installer Advanced Update.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Installer_Advanced_Update.png)

Note that the installer will by default use a shared bundle pool for creating installations. This defaults to the .p2 folder in the home folder. If the file system for the home folder is relatively small, you can change the default location using the Bundle Pools menu option in simple mode, or the right-most toolbar button in the Bundle Pool section in advanced mode, as seen in each of the corresponding screen captures in the following section.

Note also that you can choose which Java VM is used by the installation you are about to create. The installer will generally detected the JREs and JDKs installed on your system, choosing an appropriate default, and remembering it for the next time you use the installer. But failing that, the installer will stay on the product page and you must use the tool button to locate a Java VM that is suitable for the installation being created.

Apply the Platform SDK Configuration
------------------------------------

We will use a so-called Oomph [configuration](Eclipse_Oomph_Authoring.md#Automation_and_Specialization_with_Configurations "Eclipse Oomph Authoring") to automate the selection of the product and projects to provision.

If you've registered the installer to launch automatically for links with scheme `eclipse+install` as described in the previous section, you can open [this link](https://www.eclipse.org/setups/installer/?url=https://raw.githubusercontent.com/eclipse-platform/eclipse.platform.releng.aggregator/master/oomph/PlatformSDKConfiguration.setup&show=true) in a new tab and click the `Launch...` button on that page. Doing so automates the following equivalent alternative steps.

Drag and drop the [Platform SDK Configuration](https://raw.githubusercontent.com/eclipse-platform/eclipse.platform.releng.aggregator/master/oomph/PlatformSDKConfiguration.setup) link on the title area of the installer. If the installer is in simple mode, it will ask to Switch to Advanced Mode; confirm that prompt. When the configuration is successfully applied, the installer will be in advanced mode and will automatically turn to the Variables page.

NOTE: Drag and drop does not work reliable on Linux, please use the next approach if you are also facing this.

As an alternative to drag-and-drop, you can copy the [Platform SDK Configuration](https://raw.githubusercontent.com/eclipse-platform/eclipse.platform.releng.aggregator/master/oomph/PlatformSDKConfiguration.setup) link, and apply it to the installer. In simple mode, this is done via the menu action; this action will appear in the menu only if the clipboard contains a valid configuration:

![Oomph Installer Simple Apply Configuration.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Installer_Simple_Apply_Configuration.png)

In advanced mode, this is done via the left-most button in the toolbar; this button will appear in the toolbar only if the clipboard contains a valid configuration:

![Oomph Installer Advanced Apply Configuration.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Installer_Advanced_Apply_Configuration.png)

Review the Variables
--------------------

After applying the configuration, you'll be on the Variable page of the install wizard's advanced mode:

![Oomph Installer Advanced Platform SDK Variables.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Installer_Advanced_Platform_SDK_Variables.png)

Of course you can use the Back button to review the selections that were made on the previous two pages, i.e., on the Product page and the Projects page. If this is the first time you've used the installer, there will be large number of variables, but all have suitable defaults. Of particular note, you may wish to change the "Root install folder" to a different location, it defaults to your home folder, keeping in mind that this location will use a significant amount of disk space. The three so-called location rule variables, for this tutorial's example scenario, will create the installation in D:\\sandbox\\USER-HOME-CLEAN\\platform-sdk\\eclipse (Eclipse.app on Mac), the workspace in D:\\sandbox\\USER-HOME-CLEAN\\platform-sdk\\ws, and all the Git clones under D:\\sandbox\\USER-HOME-CLEAN\\platform-sdk\\git.

The long list of variables is mostly the result of the different choices available for the URI used to clone each Git repository. Currently there are six choices, but that may soon be reduced to three if the Eclipse Foundation eliminates the non-Gerrit servers. All the clone URIs for the Platform SDK Configuration's repositories default to anonymous, read-only Gerrit access. If you are a committer, or a contributor with a [Gerrit](/Gerrit "Gerrit") account, you will want to change each of these URIs to a form that allows read-write access. If you do not have a Gerrit account, you should [get one](/Gerrit#User_Account "Gerrit") immediately! When you select the SSH (read-write, Gerrit) choice, a new variable prompt, Eclipse Git/Gerrit user ID, will appear at the very bottom. Here you should enter your Eclipse account ID, e.g., for me, emerks.

Note that if you find it very painful to change each of the many URIs in the dialog, you'll only ever have to do this once, because the installer will remember this choice and will no longer display the variable, unless you check Show all variables, in which case you can change the choice you made previously. In addition, the latest version of the installer has simplified these steps. There is now a prompted variable that you can exploit to change all the prompted clone URIs to use your preferred style of authentication.

![Oomph Installer Advanced Platform SDK Variables With Style Prompt.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Installer_Advanced_Platform_SDK_Variables_With_Style_Prompt.png)

It still defaults to anonymous, but ideally you will get an Eclipse account and specify ssh.

Press the Next button.

Confirm the Tasks
-----------------

After pressing the Next button, you'll be on the Confirmation page:

![Oomph Installer Advanced Platform SDK Confirmation.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Installer_Advanced_Platform_SDK_Confirmation.png)

Here you can see all the setup tasks that must be performed before the installation can be launched. You can select each task to review its nested element structure and its properties; you can also select a nested element to review its properties. The most important task is the so-called P2 Director task, it specifies the requirements of what needs to be installed and the update sites from which to install them. Note in particular that the Platform SDK Configuration will install using the Eclipse Platform Project's most recent Integration build.

Press the Finish button and accept the license that is likely associated with the features you are about to install.

Monitor the Progress
--------------------

After pressing the Finish button, you'll be on the Progress page where you can review the progress of the tasks being performed.

![Oomph Installer Advanced Platform SDK Progress.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Installer_Advanced_Platform_SDK_Progress.png)

After the P2 Director task's repositories are loaded, when it's time to download the artifacts to install, you'll likely be prompted to accept all the specific licenses. Note that this confirmation dialog has a "Remember accepted licenses" check box, be sure to click it so that you'll never be asked to review these licenses again.

If this is the first time you've created an installation using the installer you may wish to go for a quick coffee break while the artifacts download. Be sure the Launch automatically check box is checked so that the installation will automatically be launched upon completion (in case your coffee break turned out to be longer than expected). Unfortunately the platform's integration build is not mirrored, and there are frequent new builds, so this process can take a while. Also the download.eclipse.org server sometimes gets overloaded, so if there is a timeout failure, you can press the Back button, followed by the Finish button, to resume downloading.

Provision the Workspace
-----------------------

When you get back from your coffee break, the installation will have launched and the setup engine will be working hard to provision its workspace. Note that there will be an animated button at the bottom of the window, near the right-hand side. You can press that control to bring up the Eclipse Updater dialog, so you can review the progress of provisioning the workspace:

![Oomph Installer Advanced Platform SDK Workspace Progress.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Installer_Advanced_Platform_SDK_Workspace_Progress.png)

There's nothing else you need to do. Cloning all these repositories will definitely take some time, some are very large, and the update sites might be slow, so you can go on your lunch break now because this could take 90 minutes.

Review the Result
-----------------

The end result is a workspace like this:

![Oomph Installer Advanced Platform SDK Workspace Result.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Installer_Advanced_Platform_SDK_Workspace_Result.png)

All the projects are organized into sensible working sets. All the Git clones are Gerrit enabled for easy contribution. And the setup even created a feature-based "Runtime Workspace" launcher and added it to the favorites list, so it's already in the menu. Now you can make changes to any project to fix bugs or to add new features and you can launch a runtime instance to test any of your changes.

Note that PDE's target platform for this workspace also contains binary equivalents of all projects in the workspace, so you can close any combination of projects to improve build time without causing compile errors.

Update the Installation and Workspace
-------------------------------------

Suppose you've performed these steps a few weeks ago and would like to update the installation and workspace to the latest and greatest state. Of course you can easily select all Git repositories in the Git Repositories view and do a Pull. But you can also easily update the installation and the workspace using the tool bar contributions provided by Oomph. The Perform Setup Tasks tool bar menu button is useful for this purpose:

![Oomph Perform Setup Tasks Menu Button.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Perform_Setup_Tasks_Menu_Button.png)

It launches the Eclipse Updater.

![Oomph Eclipse Updater.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/800px-Oomph_Eclipse_Updater.png)

The P2 Director task will update the installation with the latest Eclipse Platform integration build. The Modular Target task will update the target platform with the latest dependencies; it will even import new projects if there are any. The API baseline changes rarely, i.e., only between releases, so you won't need to perform the tasks for updating the API baseline nearly as frequently. Note that you can selectively enable tasks. In the above I have only enabled the first and the last task. It's very convenient to enable a single task with a double-click; all other tasks will be unchecked and only the selected task will be checked. Hitting Finish will perform the enabled tasks. By default the dialog will minimize to the status bar, where it will be visible as an animated icon. It's a non-modal dialog, so you can make it visible by clicking the status icon. The status icon will eventually disappear if the tasks perform successfully; if not, you'll need to open the dialog to see what's going on. For example, when the installation is updated, you'll need to restart the IDE, which you can do by pressing the Finish button of the wizard.

You may also wish to view the setup definitions provided for the various projects. The Open setup menu button is useful for this purpose:

![Oomph Open Setup Menu Button.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Open_Setup_Menu_Button.png)

Please refer to the [authoring guide](Eclipse_Oomph_Authoring.md#Understanding_the_Setup_Engine "Eclipse Oomph Authoring") if you're interested in the details. Many of the project setups are located within the Git clones themselves, so you can contribute changes to them, and can test the impact in the running installation; the long term goal is for each project to maintain its own project setup, but we're not quite there. In any case, you might get some good ideas for how best to author an Oomph setup for your own projects!

