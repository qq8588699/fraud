# fraud

python version: latest anaconda distribution as of 12/22/2018. 
Python 3.6.7 |Anaconda, Inc.| (default, Oct 23 2018, 19:16:44) 
[GCC 7.3.0] on linux

To run on command line 
git config user.name "YOUR_NAME"
git config user.email "pengzhou2011@gmail.com"

Basic idea of using git.
1. Clone to your local work dir (git clone https://github.com/qq8588699/fraud.git). 
   (ssh is better since http one always asks for username and password when pushing to github. However, the cluster I am using does not support ssh key, so need to stick with http. 
    You can run git clone git@github.com:qq8588699/fraud.git instead if you can use ssh key. It makes it easier to push to and pull from remote)
2. Create your own branch to work. Never work on the master branch. Branch name can be per user story
3. Commit your changes to your local branch, and then push to the same branch at remote.
4. Every commit should be of a logical change. 
5. Create a pull request from your branch to master on github once you finished a story. Everyone can review your change.
6. Everytime before you work on your own branch and make changes, always merge with master first, so that your local branch is always up to date.

Basic Structure of Project:
./resource/: contains the raw data and output of each phase in the pipeline. 
./pgm: contains the source codes which form the project pipeline. Each phase(script) is labeled by an integer number. The output should go to the corresponding dir with the same integer number in ./resource/
./pgm/.resource is the softlink to resource
We only commit source code (./pgm/) into git. We don't commit real data to git (too large). We can commit small outputs in ./resource/ though.
./notes: We updates our thoughts and project plans here. Try to keep things concise and organized.

Uncommitted files:
Softlinks are not commited
./resource/000_rawData/[train.csv,test.csv,sample_submission.csv]
