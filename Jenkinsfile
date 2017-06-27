pipeline {

    agent any
    stages {

        stage('Deploy') {
            steps {
            	script {
            		try {
			     sh "helm upgrade demo-api-${env.BRANCH_NAME} --namespace=demo-api-${env.BRANCH_NAME} --set tag=${env.BUILD_TAG} ./helm/openldap"
            		} catch (e) {
            		     sh "helm install --name=demo-api-${env.BRANCH_NAME} --namespace=demo-api-${env.BRANCH_NAME} --set tag=${env.BUILD_TAG} ./helm/openldap"
            		}
            	}
            }
        }
    }
}