
node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: 'b3c5b160-6db9-47da-b32f-7a7108676245', url: 'git@github.com:beeva-jesusneila/course-cicd.git'
  }

  stage('Test') {
    sh './simplehttpserver/tests/nittests.sh ./simplehttpserver/'
  }
}
