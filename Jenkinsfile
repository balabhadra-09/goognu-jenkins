pipeline{
    agent any 

    stages{
        stage('checkout'){
            steps{
                checkout scm
                echo "github sourse code checkout suussfuly"

            }
        }

        stages{
            stage('build'){
                steps{
                    echo "biuld succesful"
                    sh "ls -la"
                }
            }
        }

        stages{
            stage('test'){
                steps{
                 echo 'Testing application...'
                 sh 'test -f index.html'
                 sh "grep -q 'Goognu Jenkins CI/CD' index.html"
                }
            }
        }

        steges{
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
}