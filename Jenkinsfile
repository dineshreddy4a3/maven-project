node {
    stage('git checkout') {
    git 'https://github.com/AnupamaSoma/maven-project.git'
}
   stage('Build') {
    sh 'mvn package'
}
   stage('Deployment')
   {
       deploy adapters: [tomcat9(credentialsId: 'tomcat-credentials', path: '', url: 'http://172.31.216.245:8080')], contextPath: 'qaapp', war: '**\\*.war'
   }
   stage('testing')
    {
        git 'https://github.com/AnupamaSoma/FunctionalTesting.git'
        sh 'java -jar /var/lib/jenkins/workspace/scripted_pipeline/testing.jar'
    }
   
    
}
