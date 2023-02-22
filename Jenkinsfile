pipeline{
    environment {
        registry = "436634162240.dkr.ecr.us-west-2.amazonaws.com/hellodatarepo"
         registryCredential = 'jenkins-ecr-login-credentials'
         dockerImage = ''
    }
    agent any
    tools { 
        maven 'maven-3.9.0'
       
    }
        stages{
            stage('git stage'){
                steps{
                    git branch: 'jenkins-ansible-cicd', url: 'https://github.com/cloudtechmasters/springboot-maven-course-micro-svc.git'
                }
            }
            stage('build maven project '){
                steps{
                   sh 'mvn clean package'
                }
            }
          stage('Building our image') {
            steps{
                script {
                    dockerImage = docker.build registry + ":$BUILD_NUMBER"
                      }
                }
            }
        }
}
