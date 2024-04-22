pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    build()
                }
            }
        }
        stage('Deploy to DEV') {
            steps {
                script{
                    deploy("DEV", 50556)
                }
            }
        }
        stage('Tests on DEV') {
            steps {
                script{
                    test("DEV")
                }
            }
        }
        stage('Deploy to STG') {
            steps {
                script{
                    deploy("STG", 50558)
                }
            }
        }
        stage('Tests on STG') {
            steps {
                script{
                    test("STG")
                }
            }
        }
        stage('Deploy to PRD') {
            steps {
                script{
                    deploy("PRD", 50557)
                }
            }
        }
        stage('Tests on PRD') {
            steps {
                script{
                    test("PRD")
                }
            }
        }
    }
}


def build(){
        echo 'Building of node aplication is starting ...'
        bat "ls"
        bat "npm -v"
        bat "npm install --package-lock-only"
        bat "npm install"
}

def deploy(String enviroment, int port){
    echo "Deployment to ${enviroment} has started ..."
    // bat "pm2 delete ${enviroment}"
    // bat "pm2 start -n \"${enviroment}\" index.js -- ${port} "
}

def test(String enviroment){
    echo "Testing on ${enviroment} has started ..."
   // bat "npm test"
}
