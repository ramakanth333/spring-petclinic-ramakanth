pipeline{
   agent any;   
// agent {label 'jdk8'}
    stages{
        stage('github clone'){
            steps{
                git 'https://github.com/ramakanth333/spring-petclinic-ramakanth.git'
            }
        }
        stage('maven compile'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('junit artifact'){
            steps{
                junit '**/target/surefire-reports/*.xml'
            }
        }
        stage(name: 'archieve artifact'){
            steps{
                archiveArtifacts artifacts: '**/target/*.jar', followSymlinks: false
            }
        }
    }
