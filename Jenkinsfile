pipeline

any agent

stages
{

stage('cloning code')

{

steps

{git 'https://github.com/chaitanyapratap19/maven-project.git'
}
}

stage('compile my project')
{
steps
{
withMaven(jdk: 'localJDK', maven: 'localMaven') {
    sh 'mvn complile'
}}}

}
