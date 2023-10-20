pipeline {
    agent any
    tools{
        maven 'myMaven'
    }

    stages {
        stage('Checkout the Source Code') {
            steps {
                echo 'Checkout the code..........................................'
                git 'https://github.com/sajidshaikhguru/addressbook-demo.git'
            }
        }
        stage('Build The Source Code') {
            steps{
			  
                       echo 'Build the Source Code ....................................'
                       sh "mvn clean package"
					
                         
                    }
				
				}
                
            }
        }
        stage('Deploy the Application') {
            steps {
                echo 'Deploy the Application.....................................'
                deploy adapters: [tomcat9(credentialsId: 'tomcat-cred', path: '', url: 'http://18.213.4.101:8080/')], contextPath: 'addressbookssimplilearn', war: '**/*.war'
            }
        }
    }
}
