pipeline {
    agent any

    stages {
      stage('checkout') {
           steps {
              git branch: 'main', credentialsId: 'jenkins1', url: 'https://github.com/ganesh1019/ansible_project.git'
          }
        }


    stage('Execute Maven') {
           steps {
                sh 'mvn package'             
          }
        }
       
        
    stage('Ansible Deploy') {
            steps {
			   sh "ansible-playbook playbooks/install-tomcat.yaml "
            }
        }
    }
}
