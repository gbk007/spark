pipeline
{
    agent
    {
        label 'SlaveforParllelpipeline'
    }
    stages
    {
        stage ('Git Checkout SCM Stage 1')
        {
            steps
            {
                git branch: 'main', url: 'https://github.com/gbk007/spark.git'
            }
        }
        stage ('Build Stage 2')
        {
            steps
            {
                sh 'mvn clean install'
            }
        }
        stage ('Push to Artifactory Stage 3')
        {
            steps
            {
                sh 'sleep 20'   
            }
        }
        stage ('Deploy Stage 4')
        {
            steps
            {
                sh '''sudo cp /home/ec2-user/parllellpipeline/workspace/JenkinsfileSCMpipeline/target/*.war /opt/*tomcat/webapps'''
            }
        }
    }
}
