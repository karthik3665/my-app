node{
   stage('SCM Checkout'){
     git 'https://github.com/karthik3665/my-app.git'
   }
   stage('Maven compile & package'){
      // Defining the maven home path 
     def mvnHome = tool name: 'maven-3', type: 'maven'
      sh "${mvnHome}/bin/mvn package"
   }
}
