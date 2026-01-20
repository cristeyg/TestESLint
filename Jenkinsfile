pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                // Get source code, Jenkinsfile, and Ansible playbooks from your repository
                git url: 'https://github.com/cristeyg/TestESLint.git'
            }
        }
        stage('Build Application') {
            steps {
                // Use build tools like Maven, Gradle, or npm to create an artifact
                sh 'mvn clean package' // Example for a Java Maven project
            }
        }
        stage('Deploy to Environment') {
            steps {
                script {
                    // Use the Ansible plugin to run the playbook on target hosts
                    // 'ansible-tool' is the name configured in Jenkins Global Tools
                    // 'deploy.yml' is your playbook file
                    // 'inventory' specifies the target hosts
                    // 'credentialsId' refers to the ID of the configured SSH credentials
                    ansiblePlaybook tool: 'ansible-tool',
                                    playbook: 'deploy.yml',
                                    inventory: 'cris/AnsibleDeplyment/host.ini', // e.g., 'hosts.ini'
                                    credentialsId: 'privatekey'
                }
            }
        }
    }
}
