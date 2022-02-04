pipeline {
    agent any
    
    tools
    {
       maven "mymvn"
    }
     
    stages {
      stage('checkout') {
           steps {
                git branch: 'master', url: 'https://github.com/ganesh1019/ansible_project'
          }
        }


    stage('Execute Maven') {
           steps {
                sh 'mvn package'             
          }
        }
       
        
    stage('Ansible Deploy') {
            steps {
			   sh "ansible-playbook /home/ansible/playbooks/install-tomcat.yaml --user ansible --key-file /home/ansible/.ssh/id_rsa"
            }
        }
    }
}
