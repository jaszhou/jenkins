pipeline {
   agent any
   environment {
       registry = "jaszhou/mongodb"
       GOCACHE = "/tmp"
       BUILD_NUMBER = "latest"
   }
   stages {
       stage ('Deploy') {
           steps {
               script{
                   def image_id = registry + ":$BUILD_NUMBER"
                   sh "ansible-playbook  playbook.yml --extra-vars \"image_id=${image_id}\""
               }
           }
       }
   }
}
