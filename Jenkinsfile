pipeline {
    agent any
           triggers {
  pollSCM ' * * * * *'
		    }
	parameters {
  choice choices: ['DEV', 'QA', 'UAT'], name: 'ENV'
		}
 
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh '/home/gaurav/Devops/apache-maven-3.9.6/bin/mvn install'
            }
        }
        stage('Deployment') {
            steps {
                  if  [ $ENV == "DEV" ];then
                  echo "Deployed to  Dev"
cp target/key.war /home/gaurav/Devops/apache-tomcat-9.0.89/webapps
elif  [ $ENV == "QA" ];then
echo "Deployed to  Qa"
cp target/key.war /home/gaurav/Devops/apache-tomcat-9.0.89/webapps
elif  [ $ENV == "UAT" ];then
echo "Deployed to  Uat"
cp target/key.war /home/gaurav/Devops/apache-tomcat-9.0.89/webapps
fi'''
         }
      }	
    }
  }
