pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
      jdk 'Java71'
      maven 'Maven3'
  }
  stages{
       stage("Cleanup Workspace"){
             steps {
               cleanWs()
             }
       }
       stage("Checkout from SCM"){
             steps {
               git branch: 'main', credentialId: 'github', url: 'https://github.com/mory-moussa-14/First'
             }
       }
       stage("Build Application"){
             steps {
               sh "mvn clean package"
             }
       }
        stage("Test Application"){
             steps {
               sh "mvn test"
             }
       }
  }
}
