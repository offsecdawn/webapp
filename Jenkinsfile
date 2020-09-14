pipeline{
    agent any
    tools{
        maven 'MAVEN_HOME'
    }
    stages{
        stage('Initialize'){
            steps{
                echo "initialization phase"
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean install package'
            }
           
        }
    }
}
