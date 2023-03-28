pipeline
{
    agent any
    stages
    {
        stage('continuousDownload')
        {
            steps
            {
             git 'https://github.com/Shivareddygone/maven1.git'   
            }
            
        }
        stage('continuousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('continuousDeployment')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '149f8007-e95b-4bd1-804b-1691c80d6d60', path: '', url: 'http://172.31.19.217:8080')], contextPath: 'mytestapp', war: '**/*.war'
            }
        }
        stage('continuousTesting')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline1/testing.jar'
            }
        }
        stage('continuousDelivery')
        {
            steps
            {
            deploy adapters: [tomcat9(credentialsId: '149f8007-e95b-4bd1-804b-1691c80d6d60', path: '', url: 'http://172.31.28.203:8080')], contextPath: 'myprodapp', war: '**/*.war'
            }
        }
    }
 }
