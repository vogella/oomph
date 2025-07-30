

Oomph
=====

![Oomph Project Logo.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Project_Logo.png)Powered by Oomph

The [Oomph Project](https://www.eclipse.org/oomph) is dedicated to providing extensions to the Eclipse Platform that improve the user experience.

One of Oomph's showcase technologies is the [Eclipse Installer](/Eclipse_Installer "Eclipse Installer"). The installer exploits Oomph's flexible and powerful [setup engine](/Eclipse_Oomph_Authoring#Understanding_the_Setup_Engine "Eclipse Oomph Authoring") to automate the installation of applications as well as the provisioning of workspaces. For an overview of this technology in action on a very large useful example, have a look at the instructions for [Provisioning the Platform SDK](/Eclipse_Platform_SDK_Provisioning "Eclipse Platform SDK Provisioning") which creates a dedicated installation for working the source code of all projects that comprise the [Eclipse Platform's SDK](/Eclipse_Project "Eclipse Project").

Note that the latest version of the installer supports [installing Marketplace listings](/Eclipse_Installer_Marketplace#Apply_a_Marketplace_Listing "Eclipse Installer Marketplace").

Contents
--------

*   [1 Eclipse Installer](#Eclipse-Installer)
*   [2 Features](#Features)
*   [3 Update Sites](#Update-Sites)
*   [4 Authoring Setup Models](#Authoring-Setup-Models)
*   [5 Frequently Asked Questions](#Frequently-Asked-Questions)
*   [6 Getting in Touch](#Getting-in-Touch)
*   [7 Contributing to Oomph](#Contributing-to-Oomph)
*   [8 Tutorials](#Tutorials)
*   [9 Articles](#Articles)
*   [10 Videos](#Videos)

Eclipse Installer
-----------------

The [Eclipse Installer](/Eclipse_Installer "Eclipse Installer") can be used to create specialized installations and to provision customized workspaces.

![OomphSimpleInstaller2.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/OomphSimpleInstaller2.png)

Features
--------

The following technologies are supported by Oomph:

*   [Targlets](/Oomph_Targlets "Oomph Targlets") provide a more expressive, flexible, scalable, and reliable infrastructure for defining a target platform.
*   [Dynamic Working Sets](/Dynamic_Working_Sets "Dynamic Working Sets") provide the ability to create project working sets based on flexible predicates (rules) for specifying which projects should be in each particular working set.
*   [Repository Analyzer](/Oomph_Repository_Analyzer "Oomph Repository Analyzer") provides support for generating a web page with a detailed analysis of one or more p2 repositories.

Update Sites
------------

We offer three types of drops: release, milestone, and nightly. They can be found in these composite repos:

*   [http://download.eclipse.org/oomph/updates/release](http://download.eclipse.org/oomph/updates/release)
*   [http://download.eclipse.org/oomph/updates/milestone](http://download.eclipse.org/oomph/updates/milestone)
*   [http://download.eclipse.org/oomph/updates/nightly](http://download.eclipse.org/oomph/updates/nightly)

  
The following is an uber composite of the three above composites:

*   [http://download.eclipse.org/oomph/updates](http://download.eclipse.org/oomph/updates)

  
For each of the four composite repos we offer a smaller variant that contains only the latest drop:

*   [http://download.eclipse.org/oomph/updates/release/latest](http://download.eclipse.org/oomph/updates/release/latest) (contains only the latest release build)
*   [http://download.eclipse.org/oomph/updates/milestone/latest](http://download.eclipse.org/oomph/updates/milestone/latest) (contains only the latest milestone build)
*   [http://download.eclipse.org/oomph/updates/nightly/latest](http://download.eclipse.org/oomph/updates/nightly/latest) (contains only the latest nightly build)
*   [http://download.eclipse.org/oomph/updates/latest](http://download.eclipse.org/oomph/updates/latest) (contains only the latest build)

  
The single drops are individually available under **[http://download.eclipse.org/oomph/drops](http://download.eclipse.org/oomph/drops)** as follows:

![OomphDrops.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/OomphDrops.png)

Note that at most five nightly drops are kept and that milestone drops are only kept until shortly after the next release.

  

Authoring Setup Models
----------------------

Please read [Oomph Authoring Guide](/Eclipse_Oomph_Authoring "Eclipse Oomph Authoring").

  

Frequently Asked Questions
--------------------------

Please read the [FAQ](/Eclipse_Oomph_FAQ "Eclipse Oomph FAQ"), learn from the [authoring tips and tricks](/Eclipse_Oomph_Authoring#Tips_and_Tricks "Eclipse Oomph Authoring"), or revisit our [help center](http://download.eclipse.org/oomph/help).

Getting in Touch
----------------

First browse the [FAQ](/Eclipse_Oomph_FAQ "Eclipse Oomph FAQ") to see if your question has already been answered.

  
As a **user** you should post your questions and comments to the public forum:

*   Web: [https://www.eclipse.org/forums/eclipse.oomph](https://www.eclipse.org/forums/eclipse.oomph)
*   Newsgroup: [news://news.eclipse.org:119/eclipse.oomph](news://news.eclipse.org:119/eclipse.oomph)

  
You can also monitor the **developer** mailing list or discuss development topics:

*   Archive: [https://dev.eclipse.org/mhonarc/lists/oomph-dev](https://dev.eclipse.org/mhonarc/lists/oomph-dev)
*   Mail: [mailto:oomph-dev@eclipse.org](mailto:oomph-dev@eclipse.org)
*   Newsgroup: [news://news.gmane.org:119/gmane.comp.ide.eclipse.oomph.devel](news://news.gmane.org:119/gmane.comp.ide.eclipse.oomph.devel)

  
If you encounter **trouble** or miss a **feature** please:

*   Search for [existing bugzillas](https://bugs.eclipse.org/bugs/buglist.cgi?classification=Tools&list_id=8268012&product=Oomph&query_format=advanced) to avoid duplication.
*   You can [watch](https://bugs.eclipse.org/bugs/userprefs.cgi?tab=email) the `oomph-inbox@eclipse.org` user to be notified about new bugzillas.
*   If nothing else helps kindly submit a new [bug report](https://bugs.eclipse.org/bugs/enter_bug.cgi?product=Oomph&component=Setup&version=1.0.0) or [feature request](https://bugs.eclipse.org/bugs/enter_bug.cgi?product=Oomph&component=Setup&version=1.0.0&bug_severity=enhancement).

  

Contributing to Oomph
---------------------

Please read the [Oomph Contributor Guide](/Oomph_Contribution_Guide "Oomph Contribution Guide").

  

Tutorials
---------

*   [Provisioning the Platform SDK](/Eclipse_Platform_SDK_Provisioning "Eclipse Platform SDK Provisioning")
*   [Oomph Basic Tutorial](http://eclipsesource.com/blogs/tutorials/oomph-basic-tutorial/) by Jonas Helming (December 2016)
*   [Oomph setup for Xtext projects](http://www.lorenzobettini.it/2015/10/oomph-setup-for-xtext-projects) by Lorenzo Bettini (October 10th, 2015)
*   [The Eclipse Installer](https://www.youtube.com/watch?v=GRKhxroJsS8) by Martin Ambrus, a short presentation video of the Oomph-powered Eclipse Installer (August 2015)
*   [Create your own product](http://thecodingflow.com/?p=50) by Florian Thienel (July 5th, 2015)
*   [Oomph Workshop: Eclipse the Way You Want It](http://thegordian.blogspot.de/2015/06/oomph-workshop-eclipse-way-you-want-it.html) by Eike Stepper (June 21st, 2015)
*   [Using the New Eclipse Installer](http://www.lorenzobettini.it/2015/05/using-the-new-eclipse-installer) by Lorenzo Bettini (May 11th, 2015)
*   [Walk-Through with Many Examples](http://github.com/joergreichert/oomph-catalogue) by JÃ¶rg Reichert (March 22nd, 2015)
*   [How to configure Mylyn Task Queries for an Atlassian JIRA Connector with Oomph Installer](http://community.bonitasoft.com/blog/how-configure-mylyn-task-queries-atlassian-jira-connector-oomph-installer) by Aurelien Pupier (September, 2014)
*   [Quicker Start Guide for Oomph](http://blogs.itemis.de/leipzig/archives/936) by Philipp Hauer and Alexander Nittka (June 30th, 2014)
*   [Creating Custom Installations with Oomph](http://www.winklerweb.net/index.php/blog/12-eclipse/20-creating-custom-installations-with-oomph) by Stefan Winkler (April 1st, 2014)

  

Articles
--------

*   [Top 10 Eclipse Mars Features](http://eclipsesource.com/blogs/2015/06/24/top-10-eclipse-mars-features) by Ian Bull (June 24th, 2015)
*   [Using Oomph's bleeding-edge nightly builds](http://blog2.vorburger.ch/2015/06/using-oomphs-bleeding-edge-nightly.html) by Michael Vorburger (June 2015)
*   [Eclipse Installer avec Oomph](http://gradot.wordpress.com/2015/06/01/eclipse-installer-avec-oomph) by Pierre Gradot (June 1st, 2015)
*   [Install Eclipse Projects with a lot more Oomph](http://www.infoq.com/news/2015/03/eclipse-oomph) by Alex Blewitt (March 21st, 2015)
*   [Oomph: A Matter of Preference](https://www.eclipse.org/community/eclipse_newsletter/2014/november/article2.php) by Ed Merks (November 2014)
*   [Eclipse has Oomph](https://www.eclipse.org/community/eclipse_newsletter/2014/may/article3.php) by Eike Stepper (May 2014)
*   [Installer Tool ÂOomphÂ Proposed as Eclipse Project](http://jaxenter.com/installer-tool-oomph-proposed-as-eclipse-project-107676.html) by Lucy Carey (March 31st, 2014)
*   [Shoes for the Shoemaker](http://ed-merks.blogspot.fr/2014/02/shoes-for-shoemaker.html) by Ed Merks (February 14th, 2014)
*   [Eclipse Oomph bringt Schwung ins Projekt](http://jaxenter.de/eclipse-oomph-bringt-schwung-ins-projekt-12977) by Eike Stepper (June 26th, 2014)

  

Videos
------

*   [OpenDaylight Mini Summit recording of an Oopmh related presentation (June 2016)](https://www.youtube.com/watch?v=TU1zjytlwFE) Slides from this session are also available [on slideshare (faster)](http://www.slideshare.net/mikervorburger/opendaylight-developers-experience-15-eclipse-setup-hot-reload-future-plans) and [on GDocs in better quality](https://docs.google.com/presentation/d/14yLzog3OhIlVsk7Clr0Tff1YayRcFnQCUZqxHMWxiNI/)
*   [OpenDaylight.org has Oomph, Eclipse.org Installer for automated workspace provisioning (April 2016)](https://www.youtube.com/watch?v=BLW8aOh6WeQ)
*   [The Eclipse Installer](http://www.youtube.com/watch?v=GRKhxroJsS8) a short presentation video of the Oomph-powered Eclipse Installer (August 2015)
*   [Oomph: Eclipse the Way You Want It](http://www.youtube.com/watch?v=a3h76AQQKN0) a speaker pitch video for the EclipseCon France (June 2015)
*   [Interview with Eike Stepper on the Eclipse Oomph project](http://www.infoq.com/interviews/eike-stepper-eclipse-oomph-project) by Alex Blewitt (May 27th, 2015)
*   [Oomph: Eclipse the Way You Want It](http://www.infoq.com/presentations/oomph) session recording and slides from the EclipseCon North America (May 21st, 2015)
*   [Papyrus Oomph Model Refinements](http://www.youtube.com/watch?v=M6ZnL2mO88Q) by Christian Damus (July 8th, 2014)
*   [Provisioning a Papyrus Development IDE with Oomph](http://www.youtube.com/watch?v=hgKjzr2pXzI) by Christian Damus (July 6th, 2014)
*   [Oomph: Automatically Provision a Project-specific IDE](http://www.youtube.com/watch?v=_QlSosecEUo&list=UUej18QqbZDxuYxyERPgs2Fw) a video recording of the talk at the EclipseCon France (June 2014)

