pipeline{
    agent any 

    stages{
        stage('checkout'){
            steps{
                checkout scm
                echo "github sourse code checkout suussfuly"

            }
        }

         stage('build'){
                steps{
                    echo "biuld succesful"
                    sh "ls -la"
                }
            }

         stage('test'){
                steps{
                 echo 'Testing application...'
                 sh 'test -f index.html'
                 sh "grep -q 'Goognu Jenkins CI/CD' index.html"
                }
            }

         stage('deploy'){
                steps{
                   echo 'Application deployment preparation successful!'
                }
            }

    }

    post{
            success{
                echo "pipeline CI/CD successful"
            }

            failure{
                echo "pipeline CI/CD failed"
            }
        }
}