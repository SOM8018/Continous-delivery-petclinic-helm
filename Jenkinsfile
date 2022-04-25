// this jenkins file used for CD jobs
pipeline{
    agent any
    stages{
        stage("Build on K8"){
            steps{
                echo "========executing Build on K8========"
                sh 'pwd'
                sh 'cp -R Helm/* .'
                sh 'ls -ltr'
                sh 'pwd'
                sh '/usr/local/bin/helm --install petclinic-app petclinic deployment --set image.repository=registry-1.docker.io/soamibm/petclinic --set image.tag=24'
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}