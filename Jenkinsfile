pipeline {
    agent any  // Use any available agent
    

    tools {
        maven 'Maven'  // Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/shatakshig21/shatans.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }
        stage('Deploy') {
            steps {
 
               sh 'ansible-playbook ansible_backup/playbook.yml -i ansible_backup/hosts.ini'
            }
        }

                  
    }

   }
