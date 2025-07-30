

Eclipse Oomph FAQ
=================

[![Oomph Project Logo.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Project_Logo.png)](/Oomph "Oomph")[Powered by Oomph](/Oomph "Oomph")

Contents
--------

*   [1 How can I change values I've entered in the prompt dialog (e.g., my "git.user.id") once that dialog is gone?](#How-can-I-change-values-I.27ve-entered-in-the-prompt-dialog-.28e.g..2C-my-.22git.user.id.22.29-once-that-dialog-is-gone.3F)
*   [2 How can I use a SSH private key with a custom file name (different from "id\_dsa,id\_rsa")?](#How-can-I-use-a-SSH-private-key-with-a-custom-file-name-.28different-from-.22id-dsa.2Cid-rsa.22.29.3F)
*   [3 How can I use a custom SSH configuration directory?](#How-can-I-use-a-custom-SSH-configuration-directory.3F)
*   [4 How can I add my own setup files?](#How-can-I-add-my-own-setup-files.3F)
*   [5 Oomph seems to update my IDE. Should I still use standard "Check For Updates..."?](#Oomph-seems-to-update-my-IDE.-Should-I-still-use-standard-.22Check-For-Updates....22.3F)
*   [6 How can I update the installer to the newest nightly build?](#How-can-I-update-the-installer-to-the-newest-nightly-build.3F)
*   [7 How can I make Oomph install the latest Eclipse platform milestone?](#How-can-I-make-Oomph-install-the-latest-Eclipse-platform-milestone.3F)

### How can I change values I've entered in the prompt dialog (e.g., my "git.user.id") once that dialog is gone?

In your installed IDE there should be button with a blue person in the main toolbar. Please click it to open your setup preferences. All prompted values are stored as VariableTasks in there and you're able to change them. (see [Bug 428268](https://bugs.eclipse.org/bugs/show_bug.cgi?id=428268))

### How can I use a SSH private key with a custom file name (different from "id\_dsa,id\_rsa")?

In your setup preferences (see above) you have to add an "Eclipse Preferences" task to set the custom file name. The key of this node should be "/instance/org.eclipse.jsch.core/PRIVATEKEY", its value should be the name (not the path) of your private key file (e.g. "eclipse.ppk").

### How can I use a custom SSH configuration directory?

In your setup preferences (see above) you have to add an "Eclipse Preferences" task to set the custom file name. The key of this node should be "/bundle_defaults/org.eclipse.jsch.core/SSH2HOME", its value should be the fully qualified path to your SSH configuration directory.

### How can I add my own setup files?

In order to get your own setup file included, simply copy the respective *.setup file next to the Setup executable. In the case of OS X one has to manually copy this file into "Setup.app/Contents/Mac OS".

### Oomph seems to update my IDE. Should I still use standard "Check For Updates..."?

You can. But consider these differences between Oomph and standard p2:

1.  p2 does not record a **version range** for the installed units so it will update to the hihgest available version, which might not be what you want. The "Diagram Editor for Ecore" is an example where the 2.x version is not able to load diagrams created with the 1.x version. Oomph in contrast uses a p2 director that is modified to understand and respect the version ranges as specified in the setup models.
2.  p2 uses the set of currently **enabled p2 repositories** for the update, which is often not immediately obvious and can change by just trying out new URLs in the "Install New Software" dialog. Oomph in contrast uses exactly the set of repositories that's specified in the setup models.
3.  p2 will always ask you to **accept licenses**, whether you've already accepted them before or not. Oomph in contrast can remember the accepted licenses and won't bother you again. As this happens based on license UUIDs this approach is even safer because it prevents you from accidentally accept licenses with content that's just very similar but different (unintentionally or on purpose) from ones you've already accepted before.

### How can I update the installer to the newest nightly build?

Edit the eclipse-inst.ini file in the installer's root folder. Add the following two options (or change the existing ones):

 -Doomph.installer.update.url=[http://download.eclipse.org/oomph/products/latest/repository](http://download.eclipse.org/oomph/products/latest/repository)
 -Doomph.update.url=[http://download.eclipse.org/oomph/updates/latest](http://download.eclipse.org/oomph/updates/latest)

### How can I make Oomph install the latest Eclipse platform milestone?

By default, the org.eclipse.products.setup will only have simulatanous release URLs such as [http://download.eclipse.org/releases/neon](http://download.eclipse.org/releases/neon), which will not have the latest code. If you would like it to install the latest Eclipse platform milestone builds, then Open User (user.setup) and add a P2 Director with a New Repository such as [http://download.eclipse.org/eclipse/updates/4.6milestones](http://download.eclipse.org/eclipse/updates/4.6milestones).

