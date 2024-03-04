pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    build 'PES1UG21CS191-1'
                    def compileCommand = "g++ -o output test.cpp"
                    sh compileCommand
                    echo 'pipeline build successful'
                }
            }
            post {
                failure {
                    echo 'pipeline build failed'
                }
            }
        }
        
        stage('Test') {
            steps {
                // Print output of the .cpp file
                script {
                    def testCommand = "./output"
                    sh testCommand
                    echo 'pipeline test successful'
                }
            }
            post {
                failure {
                    echo 'pipeline test failed'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Your deployment steps go here
            }
            post {
                failure {
                    echo 'pipeline deployment failed'
                }
            }
        }
    }
}
