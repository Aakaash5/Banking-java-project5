pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Aakaash5/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with aakaash'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with aakaash'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with akshat'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with aakaash'){
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
