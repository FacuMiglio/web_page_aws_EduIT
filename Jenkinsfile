pipeline {
    agent any

    stages {
        stage('aws sts') {
            steps {
                echo 'aws sts'
                sh 'aws sts get-caller-identity'
            }
        }
        stage('aws s3 listar') {
            steps {
                sh 'aws s3 ls'
            }
        }
        stage('Git Clone') {
            steps {
                sh 'rm -rf web_page_aws_EduIT/'
                sh 'git clone https://github.com/FacuMiglio/web_page_aws_EduIT.git'
                sh 'ls -lrt web_page_aws_EduIT/'
            }
        }
        stage('To S3') {
            steps {
                sh 'aws s3 cp web_page_aws_EduIT s3://facum-webpage-1 --recursive'
            }
        }        
    }
}
