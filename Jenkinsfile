pipeline
{
 agent any
 stages{
    stage('Build Application'){
    steps{
    withMaven(maven : 'maven_online'){
    bat 'mvn -B -U -e -V clean -DskipTests package'
    }
   }
   } 
   stage('SonarQube Check'){
   steps{
   withMaven(maven : 'maven_online'){
    bat 'mvn sonar:sonar -Dsonar.sources=src/ -Dsonar.host.url=http://localhost:9000 -Dsonar.login=c91a76d35e003f1d1af99856195a65522c327514'
    }
   }
   }
    stage('Deploy Application To Mulesoft Cloudhub'){
    steps{
		bat 'mvn package deploy -DmuleDeploy -Danypoint.userName=OssomVictory3 -Danypoint.password=Viju@1999'
		}
   }
   }
}

} 
 
