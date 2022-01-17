gitRepo = 'https://my-repo/repo.git'

pipeline {
    agent any

    environment {
        // optional, not used below. Use only if you need to have an environment variable
        GitRepo = gitRepo
    }

  

    parameters {
        string defaultValue: gitRepo, description: '', name: 'Test', trim: false
    }

    stages {
        stage ('foo') {
            steps {
                echo 'Hi'
            }
        }
    }
}
