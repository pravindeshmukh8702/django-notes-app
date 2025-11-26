@Library('Shared')_
pipeline{
    agent { label 'vishal'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/pravindeshmukh8702/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            docker_build("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                docker_push("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
