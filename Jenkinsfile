pipeline
{
  agent any
  environment
  { 
    PATH="/opt/apache-maven-3.6.3/bin:$PATH"
  }
  stages{
    stage('clone')
    {
      steps{
      git branch: 'development', url: 'https://github.com/Rupali1520/jenkinsassignmentrepo.git'
      }}
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('deploy'){
      steps{
        sshagent(['knoldus']) {
          sh 'scp -o StrictHostKeyChecking=no knoldus@0.0.0.0:/opt/tomcat/webapps'
    
         
}
      }
    }
  }
    
  
}
