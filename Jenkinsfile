pipeline{
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
        }
}
