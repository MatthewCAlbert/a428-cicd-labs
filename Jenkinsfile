node {
    def image = 'node:16-buster-slim'
    def args = '-p 3000:3000'
    pipeline {
        agent {
            docker {
                image image
                args args
            }
        }
        stages {
            stage("Build") {
                steps {
                    sh 'npm install'
                }
            }
            stage("Test") {
                steps {
                    sh './jenkins/scripts/test.sh'
                }
            }
        }
    }
}
