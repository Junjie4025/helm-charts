node {
        stage('Clone Repository') {
            checkout scm
        }
        stage('Install new release') {
            
            withKubeConfig(caCertificate: '', 
                           clusterName: 'k8s.dev.soniamahankali.com', 
                           contextName: 'k8s.dev.soniamahankali.com', 
                           credentialsId: '9e60511a-089a-4402-9d37-4859a73fccf4', 
                           namespace: '', 
                           serverUrl: 'https://api.k8s.dev.soniamahankali.com') {
                sh "helm upgrade backend ./backend"
		sh "helm upgrade frontend ./frontend"
            }
        }
}
