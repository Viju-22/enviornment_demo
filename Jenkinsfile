pipeline
{
    agent any
    
    environment {
        env_qa = "QA"
    }
    
    stages{
        stage('Build Application'){
        steps{
        bat 'mvn clean install'
        }
      
        }
        
        stage('SonarQube Testing'){
        steps{
        bat 'mvn sonar:sonar -Dsonar.sources=src/ -Dsonar.host.url=http://localhost:9000 -Dsonar.login=c91a76d35e003f1d1af99856195a65522c327514'
            }
        }
       
        stage('Deploy to QA environment ')
        {    
            when{
                branch 'QA'
            }
        steps{
        bat 'mvn package deploy -DmuleDeploy -Danypoint.userName=OssomVictory5 -Danypoint.password=Capg@1999 -Denvironment=${env_qa}'
        }
        
        }
       
   
    }
}
