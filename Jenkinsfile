@Library("Shared") _
pipeline{
    
    agent {label "Bala"}
    
    stages{
        
        stage("Hello"){
            steps{
               script{
                hello()
               }
                
            }
        }
        
        
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/v-i-k-a-s-1-7/django-notes-app.git","main")
                }
            }
        }
        
        stage("Build"){
            steps{
                script{
                    dockerBuild("springsloth","notes-app","latest")
                }
            }
        }
        
        stage("Push to DockerHub"){
            steps{
                script{
                    dockerPush("notes-app","latest")
                }
            }
        }
        
        stage("Deploy"){
            steps{
               script{
                   deploy()
               }
            }
        }
    }
}
