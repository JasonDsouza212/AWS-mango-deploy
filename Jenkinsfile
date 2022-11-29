//  #!/usr/bin/env groovy
pipeline{
    agent any
    stages{
           stage("init"){
        steps{
            script{
                echo "initilizized";
            }
        }
    }
    stage("deploy"){
        steps{
               script {
                    def dockerCmd= 'docker run -p 3080:3080 -d jasonkd006/my-repo:1.0'
                   sshagent(['ec2-server-k']) {
                         sh "ssh -o StrictHostKeyChecking=no ec2-user@35.154.71.70 ${dockerCmd}"
                        }
                   
                }
        }
    }
    }
}