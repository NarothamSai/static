pipeline{
    agent any
    stages{
        stage('upload to AWS'){
            steps{
                withAWS(region:'us-west-2',credentials:'narotham'){
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'narotham-udagram')
                }
            }
        }
    }
}
