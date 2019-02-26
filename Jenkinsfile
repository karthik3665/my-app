node{
   stage('SCM Checkout'){
     git 'https://github.com/karthik3665/my-app.git'
   }
   stage('Maven compile & package'){
     sh 'mvn package'
   }
}
