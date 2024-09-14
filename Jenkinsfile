node {
  def myGradleContainer = docker.image('gradle:jdk8-alpine')
  myGradleContainer.pull()
  stage('SCM check y Preparacion') {
    checkout scm
  }
  stage('Testeo') {
     myGradleContainer.inside("-v /home/udemy/ci-cd/jenkins-ct/jenkins_home/.gradle:/home/gradle/.gradle") {
       sh 'cd complete && gradle test'
     }
  }
  stage('Ejecucion') {
     myGradleContainer.inside("-v /home/udemy/ci-cd/jenkins-ct/jenkins_home/.gradle:/home/gradle/.gradle") {
       sh 'cd complete && gradle run'
     }
  }
}
