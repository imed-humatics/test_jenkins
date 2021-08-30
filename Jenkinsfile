import groovy.json.JsonOutput
pipeline {
   agent any
   triggers {
      cron('* * * * *')
   }
   stages {
      stage('stage1') {
         steps {
             echo "running stage 1"
         }
      }
      stage('stage2') {
         steps {
             echo "running stage 2"
         }
      }
   }
}
