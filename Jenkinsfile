 pipeline {
 agent any
 stages {
 stage('Build') { 
steps {
 sh 'mvn -B -DskipTests clean package' 
}
}
 stage('pmd') {
 steps {
 sh 'mvn pmd:pmd'
 }
 }
 stage('test'){
  steps{
   sh' mvn test'
  }
 }
 }
  post {
 always {
 archiveArtifacts artifacts: '**/target/site/**', fingerprint: true
 archiveArtifacts artifacts: '**/target/**/*.jar', fingerprint: true
 archiveArtifacts artifacts: '**/target/**/*.war', fingerprint: true
 }
 }
 }
