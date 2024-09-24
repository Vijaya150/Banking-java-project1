pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Vijaya150/Banking-java-project1/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with vijaya'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with vijaya'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with vijaya'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with vijaya'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
