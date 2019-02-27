node{
   stage('SCM Checkout'){
     git 'https://github.com/karthik3665/my-app.git'
   }
   stage('Maven compile & package'){
      // Defining the maven home path 
     def mvnHome = tool name: 'maven-3', type: 'maven'
      sh "${mvnHome}/bin/mvn package"
   }
   stage('SonarQube analysis') {
     def mvnHome = tool name: 'maven-3', type: 'maven'
    withSonarQubeEnv('sonar-6') {
      // requires SonarQube Scanner for Maven 3.2+
       sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }
     
   stage('Email Notification'){
    mail bcc: '', body: '''Hello,

    This is a testing of email
    Thanks
    karthik''', cc: '', from: '', replyTo: '', subject: 'Testing the Jenkins email', to: 'karthik.bm179@gmail.com'
   }
   stage('Slack Notifications'){
   slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'java-pipelinedemo', color: 'good', message: 'welcome to Jenkins Slack', teamDomain: 'karthikcloud', tokenCredentialId: 'Slack'
   }
}
