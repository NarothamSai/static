pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh 'echo "Hello world"'
                sh '''
                    echo "multiline shell steps works"
                    ls -lah
                '''
            }
        }
        stage('Lint HTML'){
            steps{
                sh "tidy -q -e *.html"
            }
        }
        stage('upload to AWS'){
            steps{
                withAWS(region:'us-west-2',credentials:'narotham'){
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'narotham-udagram')
                }
            }
        }
    }
}

