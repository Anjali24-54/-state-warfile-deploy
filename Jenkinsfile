pipeline {
    agent any  // Runs on any available agent

    stages {
        stage('Git checkout') {
            steps {
                // Clone the repository containing the playbook
                git 'https://github.com/Anjali24-54/-state-warfile-deploy.git'
            }
        }

        stage('Deploy WAR File') {
            steps {
                // Run the Ansible playbook for WAR file deployment
                ansiblePlaybook(
                    credentialsId: '3a1f141a-2cee-4725-8635-9dec7b70c316',  // Jenkins credentials ID for Ansible
                    disableHostKeyChecking: true,  // Disables host key checking (use with caution)
                    installation: 'myansible',  // Ansible installation in Jenkins
                    inventory: '/home/aanza/.ansible/hosts', // Assuming inventory file is in the same repo
                    playbook: 'warfile-deploy.yml', // Playbook to be executed
                    vaultTmpPath: ''  // Leave empty if you're not using Ansible Vault
                )
            }
        }
    }
}
