pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/arun206/Banking-java-project'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with arun'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile with arun'
            }
        }
        stage('codetesting with arun'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with arun'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with arun'){
            steps{
                sh 'mvn package with arun'
            }
        }
        stage('run dockerfile with arun'){
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
