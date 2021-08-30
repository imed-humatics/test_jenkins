pipeline {
    agent any
    triggers {
        cron('*/2 * * * *')
    }
    stages {
        stage('stage1') {
            steps {
                echo "running stage 1"
                script { 
                    env.buildCauses = currentBuild.rawBuild.getCauses()
                    if (buildCauses.contains("hudson.triggers.TimerTrigger")) {
                        env.IS_PERIODIC_BUILD = "TRUE"
                    } else {
                        env.IS_PERIODIC_BUILD = "FALSE"
                    }
                }
            }
        }
        stage('stage2') {
            steps {
                echo "running stage 2"
                sh 'script.sh'
            }
        }
    }
}
