# CI-CD 
# Jenkins piple line stages and steps 
DevOps
Jenkins pipelines is set of plugins that helps in CD
jenkins pipleline is an automated process using the tools such the plugins
a pipleline is implemented in a file that is kept in the source code along with  rest of the source code. this file is called JenkinsFile
to create a pipleline add the nenkins files to the source control repo
when created the project choose pipleline or multibranch project type 
pipleline is domain specific language
it can be scripted or declarative 
below is the jenkinsFile is declarative style
Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                echo "building"
            }
        }
        stage('Test') { 
            steps {
               echo "testing"
            }
        }
        stage('Deploy') { 
            steps {
                echo "deploying"
            }
        }
    }
}

jenkinsFile consists for stages such as
-build
-test
-deplying to staging area
-production deployment
each stage is made up of steps
eg:
execute a command
-restart a service
--copy files to server
-wait for human interaction

An exmaple of a jenkisFile ins action. one stage and three steps
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon' //sh means its a shell command 
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
    }
}
