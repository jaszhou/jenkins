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
                   sh "/usr/local/bin/ansible-playbook  main.yml --extra-vars \"image_id=${image_id}\""
               }
           }
       }
   }
}
