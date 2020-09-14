pipeline{
    agent any
    tools{
        maven 'MAVEN_HOME'
    }
    stages{
        stage('Initialize'){
            steps{
                sh '''
                    echo "$PATH"
                    echo "$JAVA_HOME"
                '''
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean install package'
            }
        }
        stage('Deplot_to_Tomcat'){
            steps{
                sshagent(['tomcat']){
                    sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@ip-172-31-89-23:/opt/apache-tomcat-8.5.57/webapps/webapps.war'
                }
            }
        }
    }
}
