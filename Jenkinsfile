pipeline {
    agent any
    tools { 
        maven 'M3' 
        jdk 'jdk1.8' 
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
        stage('Git checkout') { // for display purposes 
            steps{
                
           
            git 'https://github.com/wongsonqern/SeleniumTest.git' 
        }
                                 }

       /* stage ('Build') {
            steps {
               
                bat "mvn -f spring-boot-microservice-forex-service/pom.xml  install"
            }
        }*/
         stage ('QA') {
            steps {
               
                bat "mvn -f spring-boot-microservice-forex-service/pom.xml  checkstyle:checkstyle"
            }
        }
         stage ('Report') {
            steps {
               
                bat "mvn -f spring-boot-microservice-forex-service/pom.xml site"
            }
        }
    }
}