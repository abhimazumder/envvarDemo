pipeline{
    agent any
    environment{
        USER_NAME = "Abhishek"
    }
    stages{
        stage('setting env var'){
            steps{
                echo "The Global Environment Variable \${env.USER_NAME} is ${env.USER_NAME}"
            }
        }
        stage('using script & withEnv block'){
            steps{
                script{
                    env.USER_AGE = "22"
                }
                
                echo "The Global Environment Variable \${env.USER_AGE} is ${env.USER_AGE}"
                
                withEnv(['USER_IS_ADMIN=true']){
	                echo "The Local Environment Variable \${env.USER_IS_ADMIN} is ${env.USER_IS_ADMIN}"
                }
            }
        }
        stage('local env var'){
            environment{
                USER_NUMBER = "7003299427"
            }
            steps{
                echo "The Global Environment Variable \${env.USER_NAME} is ${env.USER_NAME}"
                echo "The Global Environment Variable \${env.USER_AGE} is ${env.USER_AGE}"
                echo "The Local Environment Variable \${env.USER_NUMBER} is ${env.USER_NUMBER}"
            }
        }
        stage('check local env var scope'){
            steps{
                echo "The Global Environment Variable \${env.USER_NAME} is ${env.USER_NAME}"
                echo "The Local Environment Variable \${env.USER_NUMBER} is ${env.USER_NUMBER}"
            }
        }
        stage('environment & script block to overide'){
            environment{
                USER_NAME = "Mazumder"
            }
            steps{
                echo "The Global Environment Variable \${env.USER_NAME} is ${env.USER_NAME}"
                echo "The Global Environment Variable \${env.USER_AGE} is ${env.USER_AGE}" // before
                script{
                    env.USER_AGE = "50"
                }
                echo "The Global Environment Variable \${env.USER_AGE} is ${env.USER_AGE}" // after
            }
        }
        stage('withEnv to override'){
            steps{
                withEnv(['USER_NAME=Panda']){
                    echo "The Global Environment Variable \${env.USER_NAME} is ${env.USER_NAME}"
                }
                echo "The Global Environment Variable \${env.USER_NAME} is ${env.USER_NAME}"
            }
        }
    }
}
