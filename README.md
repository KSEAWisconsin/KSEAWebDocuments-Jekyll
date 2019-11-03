# KSEAWebDocuments
Storing all documents(paperworks, Wiki, etc) for Website rebuilding project of Korean-American Scientists and Engineers Association - Wisconsin Chapter  

After intense research on various static website builders, we decide to use Jekyll
- At now, Sep. 26. 2019, the latest version of Jeykll is **4.0.0**
- Install Jeykll **4.0.0**, following the [official guide](https://jekyllrb.com/docs/installation/)


## Procedures / Permissions
As this repository has been changed to public, I set some rules for pushing chnages to this repository

### Administrator
Permission granted to push directly to master

### CodeOwners
Someone who are responsible for code review and merge the pull request from others. But, still not granted direct push permission to master branch.  
Follow the procedures written on [Collaborators (Developers)](https://github.com/hyecheol123/KSEAWebDocuments#collaborators-developerss).

### Collaborators (Developers)
You are not allowed to pull directly to master, but you can make a new branch and write code there.  
After you make new branch with **descriptive name** including your **gitHub Username or FirstName**, you should make a pull request to master. (example of branch name: `Hyecheol_JekyllInstallProcedure`)  
After making a pull request, **CodeOnwer will check your code and merge** it to master after review. At least one review is requried.  
Note that if you submit more than one PRs from Repository, only the latest PR will be reviewed (others will be deleted). If you submit incompleted work, you can resubmit the PR after you finish your work. All new branches must be created based on the features you are working on.

- Make new branch (Convention: `NAME_DESCRIPTION`)
- Work on the new branch
- Make Pull Request (On Github Web)
- Wait for Reviews

### Others (Including Pool Members)
You are not allowed to make any changes directly on this repository, but you can still read code and make fork of this code.  
To make some contribution, please **fork** this repository and work there. Note that the the forked repository name must contains this repository name with short descriptions (Forked Repository name example: `KSEAWebDocuments_JekyllInstallProcedure`)  
After that, you can submit a pull request to this repository.  
The procedures after you submit the pull request is same as collaborators'. Read the Collaborators' Guideline located above.

- Fork this repository (Convention: `RepoName_DESCRIPTION`, On GitHub Web)
- Work on forked repository
- Make Pull Request (On GitHub Web)
- Wait for Reviews


## Contribution Evaluation
To **maintain high productivity** of team and **properly compensate** for the contribution toward this project, we decided to calculate each person's contribution rate.  
For each sub-projects and small tasks, score will be set based on the difficulty and expected work-hours to finish it.  After each task finished, the score of the task will be divided to the participants of that task considering github statistics (number of commits, number of code line editted, and so on) and other adjustments.  
Score will be maintained on separated **[ScoreBoard](https://github.com/hyecheol123/KSEAWebDocuments/blob/master/ScoreBoard.md)** documents.


## Benefit of Contribution
Depending on the score of contribution, contribution Badge will be given. By earning each contribution badge, some benefits will be given to each participants. Contributors without badge will not receive any benefit.
- **Bronze Contributors**: Score 40
  + Contributor will be creditted as ***Contributors*** of KSEA Website Rebuilding project. Their name will be placed on a page on website where describing ***KSEA-Wisconsin Webpage Rebuilding Taskforce***
- **Silver Contributors**: Score 70
  + Include all benefits of *Bronze Contributors*
  + Contributor will be creditted as ***Honored Contributors*** of KSEA Website Rebuilding project.
- **Gold Contributors**: Score 120
  + Include all benefits of *Silver Contributors*
  + Will host online resume of the participants after *Phase 2* update(TBD) of website.

## Timeline of Project
The estimated plan for this project is illustrated below
- Sep. 24: Select base open-source project that will use for this project (**Finish**)
  + We Selected **Jekyll**
- Oct. 04 ~~Oct. 05~~: Finish installing required environment (**Finish**)
- Oct. 25 ~~Oct. 19~~: Obtain basic knowledge of Jekyll (**On-going**)
- Nov. 02 ~~Oct. 19~~: Designing Website (**Finish**)
- Dec. 01: Finish Development
- Dec. 25: Test Initiated
- Jan. 20: Start service on AWS
- Mar. 15: Fixing Error, estimating cost
- May. 15: End of Project, Maintaining service


## More upcomming projects
- Phase 2
  + Make auto resume builder for KSEA-Chapter Members (Using Jekyll?)
- Phase 3
  + Implementing E-Mail Inquiry form (Using AWS Lambda and SES)
  + Implementing autonomous E-Mail Advertisement sender (Using AWS SES)
- Phase 4
  + Development Website for YG Chapter


## Contents
### Design
Containing design of the site, all of **Desktop** and **Mobile** site.  
Only final exported prototype will be stored, the working copy is maintained on the other private repository.  
- **Desktop Design**
  + *Last Update:* Oct. 27. 2019
  + *Author:* Hyecheol (Jerry) Jang  
- **Mobile Design**
  + *Last Update:* Nov. 02. 2019  
  + *Author:* Hyecheol (Jerry) Jang  

### Jekyll  
Containing document related to using (installing) Jekyll  
**Compare Data File Types**  
Supplement of **Directory Structure**  
Write about various type of data files (YAML, JSON, CSV), which jekyll uses to store variables(data) of website.
- *Last Update*: Oct. 29. 2019  
- *Author*: Yongsang Park  

**Directory Structure**  
Contains information of basic Jekyll's structure.  
Write on how it works and how each files and directory (the components) are working to generate the website.  
- *Last Update*: Oct. 30. 2019
- *Author*: Yongsnag Park, Hyecheol (Jerry) Jang  

**Process of Generating Theme**  
Review the overall procedure of making Jekyll Theme  
- *Last Update*: Oct. 17. 2019
- *Author*: Yongsang Park  

**Error While Installing Jekyll**  
This file has been generated to report errors while installing Jekyll, and report the solutions for those.  
- Failed to build gem native extension  
- ERR_CONNECTION_REFUSED while trying to access from the other device  
- *Last Update:* Sep. 27. 2019
- *Author:* Hyecheol (Jerry) Jang, Chanwoong Jhon  

**Jekyll Install Procedure (Ubuntu)**  
Containing procedures to install Jekyll, from the beginning (setting up the requirements)
- *Last Update:* Sep. 28. 2019
- *Author:* Hyecheol (Jerry) Jang


### Static Website Builder Research
Conduct research on the well-known static website builders (The one that receive more than 10K starts on github, data retrieved from [staticgen](https://www.staticgen.com/)
- Basic Description
- Features
- Reason for Choosing
- Reason for Refusing
  - **Docusaurus.md**
    + *Last Update:* Sep. 24 2019
    + *Author:* Yongsang Park, Hyecheol (Jerry) Jang
  - **Gatsby.md**
    +  Appendix (About GraphQL)
    + *Last Update:* Sep. 22. 2019
    + *Author:* Yongsang Park, Hyecheol (Jerry) Jang
  - **GitBook.md**
    + *Last Update:* Sep. 24. 2019
    + *Author:* Chaiyeen Oh
  - **Hexo.md**
    + *Last Update:* Sep. 24. 2019
    + *Author:* Yongsang Park, Hyecheol (Jerry) Jang
  - **Hugo.md**
    + *Last Update:* Sep. 22. 2019
    + *Author:* Hyecheol (Jerry) Jang
  - **Jekyll.md**
    + Octopress (static Contents Management Tool based on Jekyll)
      * Some Description
      * Feature
    + *Last Update:* Sep. 22. 2019
    + *Author:* Yongsang Park, Hyecheol (Jerry) Jang
  - **NextJS.md**
    + *Last Update:* Sep. 24. 2019
    + *Author:* Chanwoong Jhon
  - **Nuxt.md**
    + *Last Update:* Sep. 21. 2019
    + *Author:* Chaiyeen Oh
  - **VuePress.md**
    - *Last Update:* Sep. 24. 2019
    - *Author:* Yongsang Park, Hyecheol (Jerry) Jang  

**ComparingLanguages.md**  
As a further research, we compared three languages that used by the analyzed static website builders  
Comparing **Go**, **Ruby**, **JavaScript(Node.JS)**
  - Descriptions and Features of each Language
  - Pros and Cons
  - *Last Update:* Sep. 25. 2019
  - *Author:* Yongsang Park, Hyecheol (Jerry) Jang
