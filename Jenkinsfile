pipeline {

agent any

stages
{

stage('cloning code')

{

steps

{git 'https://github.com/Berad05/maven-project.git'
}
}

stage('compile my project')
{
steps
{
withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME') {
    sh 'mvn compile'
}}}
    
stage('test my project')
{
steps
{
withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME') {
    sh 'mvn test'
}}}
    
stage('package my project')
{
steps
{
withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME') {
    sh 'mvn package'
}}}
    

    
        
stage('package my install')
{
steps
{
withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME') {
    sh 'mvn install'
}}}
	
   
	
	
stage('deploy to  tomcat')
{
steps
{
    sshagent(['tomcat']) {
	 sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.17.241:/var/lib/tomcat/webapps'
						}
}
}
    
    
    

}
}
