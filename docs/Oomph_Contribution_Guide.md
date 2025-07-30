

Oomph Contribution Guide
========================

[![Oomph Project Logo.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Project_Logo.png)](/Oomph "Oomph")[Powered by Oomph](/Oomph "Oomph")

If you wish to contribute to Oomph, please obtain an [Eclipse Gerrit account](http://wiki.eclipse.org/Gerrit#User_Account) and provision your Oomph setup to use a Gerrit clone. Then you'll be able to commit your contribution to Gerrit for review. You'll also need an [Eclipse account](https://dev.eclipse.org/site_login/createaccount.php) for bugzilla access and to post to the [forums](/Eclipse_Oomph_Installer#Getting_in_Touch "Eclipse Oomph Installer").

Here are some simple rules to follow for contributing to Oomph:

1.  All contributions should correspond to a [bug report](https://bugs.eclipse.org/bugs/enter_bug.cgi?product=Oomph&component=Setup&version=1.0.0) or [feature request](https://bugs.eclipse.org/bugs/enter_bug.cgi?product=Oomph&component=Setup&version=1.0.0&bug_severity=enhancement) and each commit message should be prefixed using that bugzilla ID, i.e., \[<bugzilla-id>\].
2.  All code comments should be well-formed, grammatically-complete English sentences, e.g., they should start with an uppercase word and end with a period.
3.  All code should follow generally accepted [Java naming conventions](http://java.about.com/od/javasyntax/a/nameconventions.htm).
4.  All code should use the automatically enforced formatting rules so new projects are generally best created via the "Oomph->Copy Project" context menu action for an existing project.

Contents
--------

*   [1 Getting the source](#Getting-the-source)
*   [2 Contributing via Gerrit](#Contributing-via-Gerrit)
*   [3 Building](#Building)
*   [4 Where to find build artifacts](#Where-to-find-build-artifacts)

Getting the source
------------------

To provision the same development environment that the Oomph developers use follow these simple steps:

1.  Download and start Oomph's [Eclipse Installer](Eclipse_Installer.md "Eclipse Installer").
2.  Drag [this link](http://git.eclipse.org/c/oomph/org.eclipse.oomph.git/plain/setups/configurations/OomphConfiguration.setup) and drop it on the installer's title area. Alternatively, copy the location of the previous link and apply it to the Eclipse Installer either via the menu in the upper right in simple mode or via the left-most toolbar button to the upper right in advanced mode.
3.  Review and/or edit the variable values that the installer presents.
4.  Click the Next/Finish buttons until the installation starts.

Contributing via Gerrit
-----------------------

Please refer to [Gerrit](/Gerrit "Gerrit").

Building
--------

cd org.eclipse.oomph
mvn -e clean verify -DskipTests=true

  

Where to find build artifacts
-----------------------------

E.g. Linux 64 bit installer build is located under: org.eclipse.oomph/products/org.eclipse.oomph.setup.installer.product/target/products/org.eclipse.oomph.setup.installer.product/linux/gtk/x86_64

The update site for the installer is located under: org.eclipse.oomph/products/org.eclipse.oomph.setup.installer.product/target/repository

The update site for the oompf plugins is located under: org.eclipse.oomph/sites/org.eclipse.oomph.site/target/repository

