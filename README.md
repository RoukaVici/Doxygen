# Online documentation

## Disclaimer
This repository, although it is comprized in the RoukaVici's organization, it is a repository especially used for an internal use of the RoukaVici's staff. Therefore, this repository should be ignored for all other users that are non part of the Roukavici organization.

On top of that, the online documentation is build through Doxygen. For more information: http://www.stack.nl/~dimitri/doxygen/

## Repossitory's architecture
In order to get an automated update for the technical online documentation, some configurations have been done from the webserver part. However some configurations have also been done from the repositories related to the technical online documentation http://163.5.84.213/doc/.

Therefore, in order to get a correlation between both parts, we had to create an alternative repository, e.g. `RoukaVici/Doxygen`. This repository is, for the moment, composed of:
- doc.tar
- Doxyfile
- Introduction.md

Thus, this repository must always have this architecture. On top of that,  each file should have the exact same name to the enumerated above in order to work with the configurations from the webserver part. This is extremely important !

## Files

### doc.tar file

`doc.tar` file is an archive that only contains the data corresponding to the output of Doxygen. Therefore, in order to create this archive with the corresponding data,  you must follow the steps of the `doc.tar` section.

### Doxyfile
The `Doxyfile` is the file that corresponds to the configuration of our actual online documentation. This file can be either open from `cli`, e.g. with emacs, or from a exclusive Doxygen GUI, `doxywizard`.

We highly recommend to open this file with doxywizard for a better readability of all the configurations we have done in the `Doxyfile`. 

### IntroductionDOTmd
`Introduction.md` corresponds to the file that acts as an `index.html`. This file should contain all information that are useful for the users.

## How to use

### git clone RoukaVici/Doxygen
First of all, you have to git clone the repository `RoukaVici/Doxygen`.

### Create a temporary repository
- Once the `git clone` performed, you to create a temporary repository. This temporary repository should not be created within the `Doxygen` repository but outside. This repository is created in order to avoid any conflict for the next steps.
- Once the temporary repository created, you have to enter in this temporary repository. I.e. `cd your_temporary_repository`.

### git clone all the concerned repositories

Once you are in your temporary reposiotry, you should `git clone` all the repositories that contain codes with comments that are compliant with Doxygen, and directly related to the RoukaVici organization. I.e:

- `RoukaVici/Asset-Unity` -> https://github.com/RoukaVici/Asset-Unity
- `RoukaVici/LibRoukaVici` -> https://github.com/RoukaVici/LibRoukaVici
- `RoukaVici/Asset-Unreal-Engine` -> https://github.com/RoukaVici/Asset-Unreal-Engine
- `RoukaVici/bluetooth-serial-port` -> https://github.com/RoukaVici/bluetooth-serial-port
- `RoukaVici/Arduino` -> https://github.com/RoukaVici/Arduino

__WARNING__ You only have to `git clone` the repositories you did not work with, and move `mv` or copy `cp` the repository(ies) you work with, and therefore, added some updates and comments within this temporary repository.

I.e., the actual architecture of your temporary repositories shoud be:
- your_temporary_repository
-- your_moved_or_copied_repositories_where_updates_and_comments_have_been_done
-- git_cloned_repositories

### Copy the Doxyfile and the introductionDOTmd files
In order to run `Doxygen` in our temporary repository you must move `mv` or copy `cp` the `Doxyfile` located in `Doxygen` repository - the cloned one - to temporary_repository. The same behavior must be done with `Introduction.md`

Once the files moved or copied in `temporary_repository`, the architecture of `temporary_repository` should be:
- your_temporary_repository
-- your_moved_or_copied_repositories_where_updates_and_comments_have_been_done
-- git_cloned_repositories
-- Doxyfile
-- Introduction.md

### Run Doxygen from either CLI or GUI
We are now eligible to run Doxygen, either the CLI or the GUI approach. For more information read the section Files -> Doxyfile.

### Create the updated version of doc.tar
After running the Doxygen, you should see a repository created within `temporary_repository`, which is `docs`.

Still in the `temporary_repository`, you should use this command: `tar -cvf docs/* doc.tar`. This command will create the new, and updated version of the actual doc.tar contained in the `Doxygen` repository.

### Finish the process
Therefore, in order to finish all the process, from the `temporary_repository` you should move `mv` or copy `cp`:
- doc.tar (THE NEW VERSION !)
- Doxyfile (In the case you add some modifications)
- Introduction.md (In the case you add some modifications)

Once the move or copy performed, all you hav to do is to go within the `Doxygen` repository and performed the git commands:
- git add (New or modified files)
- git commit (your messages)
- git push





That's all folks
