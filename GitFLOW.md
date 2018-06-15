
Git is not a trivial tool to get used to. Junior developers also need a bit of practice before getting familiar with it. But understanding the core functionality of git does not require a degree in computer science nor years of programming experience.

####Top tips:
Git workflow dictates what kind of branches to set up and how to merge them together.
When committing, write a title and a description with the changes you made.
The master branch stores the official release history, and the DESIGN branch serves as an integration branch for features. It's also convenient to tag all commits in the master branch with a version number.

####The FLow
1. The first step is to complement the default master with a DESIGN branch. A simple way to do this is for one designer to create an empty DESIGN branch locally and push it to the server
This branch will contain the complete history of the project, whereas master will contain an abridged version. 

2. Each new feature should reside in its own branch, which can be pushed to the central repository for backup/collaboration. But, instead of branching off of master, FEATURE branches use DESIGN as their parent branch. When a feature is complete, it gets merged back into DESIGN. Features should never interact directly with master.
FEATURE branches are generally created off to the latest DESIGN branch.

3. When you’re done with the work on the feature, the next step is to merge the feature_branch into DESIGN.

4. Once DESIGN has acquired enough features for a release, you fork a release branch off of DESIGN. Creating this branch starts the next release cycle, so NO new features can be added after this point—only bug fixes, documentation generation, and other release-oriented tasks should go in this branch. Once it's ready, the release branch gets merged into master and tagged with a version number. In addition, it should be merged back into develop, which may have progressed since the release was initiated.
Using a dedicated branch to prepare releases makes it possible for one team member to polish the current release while another continues working on features for the next release.

5. Once the release is ready to go live, it will get merged it into MASTER and DESIGN, then the RELEASE branch will be deleted. It’s important to merge back into DESIGN because critical updates may have been added to the RELEASE branch and they need to be accessible to new features.


####In the nutshell:
    A DESIGN branch is created from master
    A RELEASE branch is created from DESIGN
    FEATURE branches are created from DESIGN
    When a FEATURE is complete it is merged into the DESIGN branch
    When the RELEASE branch is done it is merged into DESIGN and MASTER
    If an issue in MASTER is detected a hotfix branch is created from MASTER
    Once the hotfix is complete it is merged to both DESIGN and MASTER
