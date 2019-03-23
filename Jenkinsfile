pipeline {
     agent any
     triggers {
          pollSCM('* * * * *')
     }
     stages {
          stage("Checkout") {
               steps {
                    git url: 'https://github.com/temp09/docker-container.git'
               }
          }
           /* stage("Clean Up Build") {
               steps {
                    bat "gradle clean"
               }
          }
          stage("Build") {
               steps {
                    bat "gradle build"
               }
          } */
          stage('Docker build') {
                                 steps {
                                      bat 'docker build -f Dockerfile -t amdad/catnip_v1 .'
                                 }
                            }
          stage('Docker push') {
                                 steps {
                               bat 'docker login -u amdad -p Mywork@098'
                               bat 'docker push amdad/catnip_v1'
                                 }
          }
           /* stage("Unit test") {
                         steps {
                              bat "gradle test"
                         }
          } */
          /* stage("Deploy to staging") {
               steps {
                    bat 'docker container ls'
                    //bat 'docker container rm -f calculator_v3'
                    bat 'docker run -d --rm -p 8765:8080 --name calculator_v4 amdad/calculator_v5'
               }
          } */
          /* stage("Acceptance test") {
                         steps {
                              sleep 60
                              bat "acceptance_test.sh"
                         }
          }
          stage('SonarQube analysis') {
                      steps {
                          script {
                              withSonarQubeEnv('sonarQube') {
                                  bat 'gradle --info sonarqube'
                              }
                          }
                      }
          }*/

     }
    /* post {
          always {
               mail to: 'amdad71@yahoo.com',
               subject: "Completed Pipeline: ${currentBuild.fullDisplayName}",
               body: "Your build completed, please check: ${env.BUILD_URL}"
          }
     }*/
}