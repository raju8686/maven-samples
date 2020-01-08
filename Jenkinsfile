node{
  stage ('Build') {
     git url: 'https://github.com/raju8686/maven-samples.git'
     withMaven(
        maven: 'Maven_01',
        mavenSettingsConfig: '299856e8-8756-40e3-aa52-c3c8c11c952a') {
        sh "mvn clean verify"      
    } 
  }
  stage ('deploy') {
       sh "sudo docker rm -f mytomcat"
         sh "sudo docker run -d --name mytomcat -p 81:8080 tomcat"
         sh "sudo docker cp /var/lib/jenkins/workspace/Pipeline_01/multi-module/webapp/target/webapp.war mytomcat:/usr/local/tomcat/webapps"
}
}
