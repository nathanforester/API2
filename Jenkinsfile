pipeline {
    agent any
    parameters {
        booleanParam(name: 'Refresh',
                    defaultValue: false,
                    description: 'Read Jenkinsfile and exit.')
		    }
    stages {
        // stage('Pre') { hello push
        //     steps {
        //         sh 'ansible-playbook -v -i /home/jenkins/.jenkins/workspace/FlaskApp/inventory.yaml /home/jenkins/.jenkins/workspace/FlaskApp/playbook.yaml'
        //     }
        // }
        // stage('Test') { 
        //     steps {
        //         sh 'sudo pytest /home/jenkins/.jenkins/workspace/FlaskApp/'
        //     }
        // }
        stage('Building') {
            steps {
                sh 'sudo docker-compose build'
            }
        }
        stage('Deploying') {
            steps {
                sh '''
                    sudo docker-compose -f /home/ubuntu/APIPrimeAge/docker-compose.yaml down                  
                    sudo docker-compose -f /home/ubuntu/APIPrimeAge/docker-compose.yaml build
                '''
            }
        }
    }
}
