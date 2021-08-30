import groovy.json.JsonOutput
pipeline {
   agent any
   triggers {
      cron('*/10 * * * *')
   }
    script{ 
        env.buildCauses = currentBuild.rawBuild.getCauses()
        if (buildCauses.contains("hudson.triggers.TimerTrigger")){
            env.IS_PERIODIC_BUILD = "TRUE"
        } else {
            env.IS_PERIODIC_BUILD = "FALSE"
        }
    }
   stages {
      stage('stage1') {
         steps {
             echo "running stage 1"
                echo "Periodic: ${env.IS_PERIODIC_BUILD}"
         }
      }
      stage('stage2') {
         steps {
             echo "running stage 2"
                         echo "Periodic: ${env.IS_PERIODIC_BUILD}"
}
      }
   }
}
