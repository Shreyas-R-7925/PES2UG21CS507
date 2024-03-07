pipeline{
    agent any 
        stages{
              stage('clone repository'){
                steps{
                    checkout([$class:'GitSCM',
                    branches:[[name:'*/main']],
                    userRemoteConfigs: [[url:'https://github.com/Shreyas-R-7925/PES2UG21CS507.git']]])
                }
              }
              stage('Build'){
                steps{
                    build 'PES2UG21CS507-1'
                    sh 'g++ Jenkins.cpp -o output'
                    echo 'Build Stage Successful'
                }
              }
              stage('Test'){
                steps{
                    sh './output'
                    echo 'test stage successfully'
                }
              }
              stage('Deploy'){
                steps{
                    echo 'deployment successfull'
                }
              }
        }
        post{
            failure{
                echo 'pipeline failed'
            }
        }
    }
