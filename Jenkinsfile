@Library('Shared')_
pipeline{
    agent { label 'vinod'}
    
    stages{
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/Kalimnawaz/django-notes-app.git", "main")
                }
            }
        }
        stage('Build') {
            steps {
                script{
                    build("notes-app","latest","kalimnawaz")
                }
            }
        }
        stage('DockerPush') {
            steps {
              script{
                  dockerpush("notes-app","latest","kalimnawaz")
              }
            }
        }
        stage('Deploy') {
            steps {
                sh "docker compose up -d"
            }
            }
        }
        
    }
