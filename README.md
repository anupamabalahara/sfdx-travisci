1. Create a Git Hib
https://github.com/anupamabalahara/sfdx-travisci

2. Cloned sfdx-travisci into my GitHub account
git clone https://github.com/anupamabalahara/sfdx-travisci.git

3. Create a Travis account and authorize Travis to login into GitHub

4. Installing Travis CI and SLDX CI

5. Using OpenSSL create a certificate

6. Login to Dev Hub using SLDX and Create a connected App in Salesforce which uses the above certificate and can be used to connect to the Dev Hub
sfdx force:auth:web:login -d -a DevHub
sfdx force:org:list

travis env set CONSUMER_KEY=<connected app consumer key>

travis env set JWT_KEY_FILE=<your server.key path>

travis env set HUB_USERNAME=<your Dev Hub username>

sfdx force:auth:jwt:grant --clientid ${CONSUMER_KEY} --username ${HUB_USERNAME} --jwtkeyfile ${JWT_KEY_FILE} --setdefaultdevhubusername


7. In YAML file, add in the required SLDX scripts which will be run a change is pushed into Git

8. Git push commands 
git add .
git commit -m "Updated YAML"
git push origin master
git checkout BranchingOut


