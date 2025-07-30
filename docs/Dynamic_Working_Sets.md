

Dynamic Working Sets
====================

[![Oomph Project Logo.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Oomph_Project_Logo.png)](/Oomph "Oomph")[Powered by Oomph](/Oomph "Oomph")

Contents
--------

*   [1 Description](#Description)
*   [2 Download/Installation](#Download.2FInstallation)
*   [3 User manual](#User-manual)
    *   [3.1 Predicates](#Predicates)

Description
-----------

Dynamic working sets is another way to define working sets. Instead of clicking together the projects belonging to a working set, the working sets are defined with a set of rules. For example you can define that projects will belong to a working set if their name matches a specific pattern. In addition to the name, it is possible to define predicate that work on the project nature, on the project builder, on the presence of a specific file with a specific content. There is also a set of logical operator predicates (and, or, notâ¦) to combine different predicate together.

![Dynamic Working Set Preferences Editor.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Dynamic_Working_Set_Preferences_Editor.png)

Dynamic working sets can be used as part of the [Eclipse Installer](Eclipse_Installer.md "Eclipse Installer") (by Oomph) tools or standalone.

Download/Installation
---------------------

The easiest way to install the "Dynamic working sets" feature is to use the Oomph update site.

Copy the "Composite Update Site" url corresponding to the version you want to install from the [http://download.eclipse.org/oomph/updates](http://download.eclipse.org/oomph/updates). To find the correct feature you can add the filter "Dynamic working sets".

![Install Dynamic Working Sets.png](https://raw.githubusercontent.com/vogella/oomph/master/docs/images/Install_Dynamic_Working_Sets.png)

User manual
-----------

You can define your dynamic working sets in the preferences: Oomph > Dynamic Working Sets. Click on the "Edit..." button.

### Predicates

*   Exclusion/Inclusion predicate
*   Name predicate
*   Repository predicate
*   Nature predicate
*   Builder predicate
*   File predicate

Logical operators:

*   And predicate
*   Or predicate
*   Not predicate

