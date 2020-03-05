pipeline {
    agent any
        stages{
            stage('Git Checkout'){
                steps{
                    git 'https://github.com/atulrockzz/parking_frontend.git'
                }
            }
            stage('Build') {
                steps{
                    sh 'npm install'
                    sh 'npm run build'
                    sh 'npm audit fix'
                }
            }
            stage('Deploy'){
                steps{
                    sh 'cp -r $WORKSPACE/build /var/jenkins_home/workspace'
                    sh 'curl -u admin:admin http://52.66.203.57:8888/manager/reload?path=/build'
                }
            }
            }
        }
