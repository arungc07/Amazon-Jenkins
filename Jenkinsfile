pipeline {
    agent any
    environment {
        // Use PATH+EXTRA to append to PATH properly
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull') {
            steps {
                git branch: 'main', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
            }
        }
        stage('echo') {
            steps {
                sh 'echo "build will start"'
            }
        }
        stage('clean') {
            steps {
                sh 'mvn clean'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }  
    }

  post{

  success{
     echo 'Build success'
  }
    
  failure{
       echo 'build failure'
   }

  }


}
