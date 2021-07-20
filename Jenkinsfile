pipeline{
    
    agent any
    
    environment{
        color_success = "#00FF00"
        color_fail = "#FF0000"
    }

    stages{
        stage('get_commit_details') {
        steps {
            script {
                env.GIT_COMMIT_MSG = sh (script: 'git log -1 --pretty=%B ${GIT_COMMIT}', returnStdout: true).trim()
                env.GIT_AUTHOR = sh (script: 'git log -1 --pretty=%cn ${GIT_COMMIT}', returnStdout: true).trim()
                BRANCH_NAME = BRANCH_NAME.replaceAll("/","-")
            }
        }
    }

        stage('Build'){
            steps{
                echo 'build....'

            }
        }
}
