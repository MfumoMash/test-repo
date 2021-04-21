pipeline{

    agent{
        node{
            label 'linux'
        }
    }

    environment {
        npmrepo = "https://nexus.nednet.co.za/repository/npm-group"
        DISTR = "${WORKSPACE}/dev"
    }

    stages{

        stage("NPM INSTALL")
        {
            steps{
                script{
                    sh "npm install --registry ${env.npmrepo}"
                }
            }
        }

        stage("BUILD")
        {
            steps{
                script{
                    sh "npm run ng build -- --outputPath=${DISTR}"
                }
            }
        }
    }

}