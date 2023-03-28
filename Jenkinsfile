pipeline {
    agent any
    environment {
        myVar = "outer block"
    }
    stages {
        stage('checkout') {
            steps {
                git branch: 'main', credentialsId: 'sumanthmachgithubid', url: 'https://github.com/Sumanthmacherla7/master.git'
            }
        }
        stage('Build') {
            steps {
                sh "sh array.sh"
            }
        }
        stage('Post Tasks') {
            steps {
                sh "echo Emailing"
            }
    
        }
        stage('Printing Environment Var') {
            environment {
                myVar = "Inner Block"
            }
            steps {
                sh 'echo "This is my variable: $myVar"'
            }
        }
    }

}
