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
    bat 'mvn sonar:sonar -Dsonar.sources=src/ -Dsonar.host.url=http://localhost:9000 -Dsonar.login=cb1af3b8b920c74b2d173d766f78366c0bea2568'
    }
   }
   }
    stage('Deploy Application To Mulesoft Cloudhub'){
    steps{
    withMaven(maven : 'maven_online'){
    bat 'mvn deploy -DmuleDeploy'
    }
   }
   }
}

} 
 
