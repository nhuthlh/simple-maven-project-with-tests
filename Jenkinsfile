node ('master') {
checkout scm
stage('Build') {
withMaven(maven: 'M3') {The New Jenkins Chapter 3
[ 124 ]
if (isUnix()) {
sh 'mvn -Dmaven.test.failure.ignore clean package'
}
else {
bat 'mvn -Dmaven.test.failure.ignore clean package'
}
}
}
stage('Results') {
junit '**/target/surefire-reports/TEST-*.xml'
archive 'target/*.jar'
}
}
