pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('Deploy to Cloudhub') {
      steps {
        sh 'mvn package deploy -DmuleDeploy -DapplicationName=mule-worldtime-api -Dworkers=1 -Dusername=gonmule -Dpassword=Traiano98dc -DworkerType=Micro -Denvironment=Sandbox -DmuleVersion=4.4.0 -DOSv2=true -Denv=dev -Dsecure.key=Scipio235ac!'
      }
    }

    stage('Test') {
      steps {
        sh 'newman run mule-worldclock-api-postman-collection.json'
      }
    }

  }
}