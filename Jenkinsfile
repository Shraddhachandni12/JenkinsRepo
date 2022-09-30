pipeline {
 tools {
     jdk 'myjava'
     
 }   
    // agent sectiom is mandatory
    agent any
    stages {
         stage ('clone the repo')
         {
             steps {
                  git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
             }
         
            
            
        }
        
        stage ('compile the code')
        {
            steps {
                sh 'mvn compile'
            }
            
        }
        
        stage ('review the code')
        {
            steps {
                sh 'mvn pmd:pmd'
            }
        }
        
        stage ('unit test')
        {
              steps{
                  sh 'mvn test'
              }
              post {
                  success {
                      junit 'target/surefire-reports/*.xml'
                  }
              }
        }
        stage ('package')
        {
            steps {
                sh 'mvn package'
            }
        }
            
        }
        
}
       
    
