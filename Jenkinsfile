pipeline {
environment {
registry = "mahiramesh2617/mahirepo"
registryCredential = 'Mahi@2617'
dockerImage = 'httpdnew'
}
agent any
stages {
stage('Cloning our Git') {
steps {
git 'https://github.com/ramesh2617/Docker.git'
}
}
stage('Building our image') {
steps{
script {
dockerImage = docker.build registry + ":$BUILD_NUMBER"
}
}
}
stage('Deploy our image') {
steps{
script {
docker.withRegistry( '', registryCredential ) {
dockerImage.push()
}
}
}
}
stage('Cleaning up') {
steps{
sh "docker rmi $registry:$BUILD_NUMBER"
}
}
}
}
