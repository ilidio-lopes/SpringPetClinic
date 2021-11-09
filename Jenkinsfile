pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('Checkpout'){
            steps{
                git branch: 'main', url: 'https://github.com/ilidio-lopes/SpringPetClinic.git'
            }
        }
        stage('Build'){
                steps{
                    sh 'mvn compile'
                }
            }
            stage('Test'){
                steps{
                    sh 'mvn test'
                }
            }
            stage('Package'){
                steps{
                    sh 'mvn package'
                }
            }
            stage('Deploy'){
                steps{
                    sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
                }
            }
        }
    
}
