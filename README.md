# postman-newman-jenkins
This test is do mock verification on Newman and Jenkins integartion.

Steps-
1. Create API
2. Save collection
3. Create package.json - npm init
4. Add newman as npm dependency- npm install newman --save
5. Delete node module folder- rm -rf -- node_modules/
6. Update package.json
	- rm: index
	- up: "test" by 
	- rm: License
7. Add to Git
	- git init
	- git add --all
	- git commit -m ""
	- Create repo on git
	- Execute: git remote add origin https://github.com/tanzyy/postman-newman-jenkins.git
	- Execute: git push -u origin master
8. Install Jenkins with NPM
	- https://hub.docker.com/r/schlechtweg/jenkins-nodejs/
9. Pipeline
	Add script
		node {
   			stage('API Tests') {
       			git 'https://github.com/tanzyy/postman-newman-jenkins.git'
       			sh 'npm install'
       			sh 'npm run api-tests-production'
   			}
		}
