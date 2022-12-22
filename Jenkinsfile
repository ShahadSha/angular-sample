pipeline {
    agent any 
    
    stages {
        stage("Clone Project") {
            steps {
                git branch: 'main', credentialsId: 'gitlab', url: 'https://gitlab.com/shahadsha1/sample-angular'
            }
        }

        stage("Building Project") {
            steps {
                script {
                    sh 'npm install'
                    sh 'ng build'
                }
            }
        }

        stage("Moving Project") {
            steps {
                script {
                    sh 'yes | cp -i -r ./dist/angular-tour-of-heroes/ /srv/mysite'
                }
            }
        }
        
    }
}