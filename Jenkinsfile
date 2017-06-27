pipeline {

    agent any
    stages {

        stage('Deploy') {
            steps {
            	script {
            		try {
			     sh "helm upgrade sso-${env.BRANCH_NAME} --namespace=sso-${env.BRANCH_NAME} --set tag=${env.BUILD_TAG} ./helm/openldap"
            		} catch (e) {
            		     sh "helm install --name=sso-${env.BRANCH_NAME} --namespace=sso-${env.BRANCH_NAME} --set tag=${env.BUILD_TAG} ./helm/openldap"
            		}
            	}
            }
        }
    }
}