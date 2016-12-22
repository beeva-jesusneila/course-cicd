
node('master') {
  stage('Checkout') {
    deleteDir()
    git credentialsId: 'b3c5b160-6db9-47da-b32f-7a7108676245', url: 'git@github.com:beeva-jesusneila/course-cicd.git'
  }

  stage('Test') {
    sh './simplehttpserver/tests/unittests.sh ./simplehttpserver/'
  }

  stage('Package and publish') {
    sh "tar -zcvf simplehttpserver-${env.JOB_NAME}-${env.BUILD_ID}.tar.gz ./simplehttpserver"
    sh "aws s3 cp simplehttpserver-${env.JOB_NAME}-${env.BUIL_ID}.tar.gz s3://clase-gendevops2-cicd-ci/"
  }
}
