pipeline {
agent any
tools {
maven 'maventest'
jdk 'JDK'
}
stages {
stage('Checkout') {
steps {
git branch: 'master', url: 'https://github.com/vibhag2005/maven234.git'
}
}
stage('Build') {
steps {
sh 'mvn clean package'
}
}
stage('Test') { 
steps {
sh 'mvn test'
}
}
stage('Run Application') {
steps {
// Start the JAR application
sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
}
}
}
post {
success {
echo 'Build and deployment successful!'
}
failure {
echo 'Build failed!'
}
}
}
