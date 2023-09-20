node{


properties([pipelineTriggers([pollSCM('* * * * *')])])


def mavenHome=tool name: 'Maven version 3.9.3'

stage('CheckOutCode'){
git credentialsId: '2fe7a80b-81c9-4342-adf7-024514f07f95', url: 'https://github.com/reddymraviteja/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}

stage('UploadArtifactsInotNexus'){
sh "${mavenHome}/bin/mvn clean  deploy"
}


stage('DeploAppIntoTomcatServer'){
sshagent(['331ae6af-906c-4d4f-8317-0379a46b437e']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.2.79:/opt/tomcat9/webapps/"
}
}

stage {'sendemail'} {
emailext body: '''Thanks & Regards,
Jenkines User''', recipientProviders: [buildUser()], subject: 'Jenkins Build', to: 'reddymraviteja@gmail.com'
}
*/
}
