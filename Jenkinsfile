pipeline
{
    agent any
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
       
        stage('Deploy Application To Mulesoft '){
        steps{
		configFileProvider([configFile(fileId: 'e3590969-51e7-48ca-948d-8e3d73287173', variable: 'MAVEN_GLOBAL_SETTINGS')])
		{
        bat 'mvn package deploy -DmuleDeploy'
        }
        }
        }
       
   
    }
}
