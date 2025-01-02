pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/akshu20791/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with aman'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with aman'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with aman'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with aman'){
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
                sh 'docker run -dt -p 9090:9090 --name c01 myimg'
            }
        }   
    }
}
