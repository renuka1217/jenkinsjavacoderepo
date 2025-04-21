pipeline{
tools{
maven 'mymaven'
}
agent any
stages{
stage ('Clone a repo')
{
steps {
git credentialsId: 'renuka1217', url: 'https://github.com/renuka1217/jenkinsjavacoderepo.git', branch: 'main'
}
}
stage ('Package the code')
{
steps{
sh 'mvn package'
}
}
stage ('Deploy the code')
{
steps{
deploy adapters: [tomcat9(credentialsId: 'tomcat-id', path: '', url: 'http://localhost:9090/')], contextPath: null, war: '**/*.war'
}
}
}
}
