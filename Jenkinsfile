pipeline
{
    agent any
    stages{
        stage('Build Application'){
        steps{
        bat 'mvn clean install'
        }
       
        }
       
        stage('Deploy Application To Mulesoft '){
        steps{
        bat 'mvn package deploy -DmuleDeploy -Danypoint.userName=OssomVictory4 -Danypoint.password=Capg@1999'
        }
       
        }
       
   
    }
}
