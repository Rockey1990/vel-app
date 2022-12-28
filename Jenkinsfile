pipeline {

         agent {
                 label {
                          label 'built-in'
                          customWorkspace '/data/pipeline'
                       }
               }
   stages {
              stage ('install httpd') {
              steps { 
                       sh "yum install httpd -y"
                                      }
                    }
 stage ('start  httpd') {
              steps {
                       sh "service httpd start"
                                      }
                    }
 stage ('copy-index') {
          steps {
                sh "cp -r index.html /var/www/html/index.html"
                sh "chmod -R 777 /var/www/html/index.html"
                }
              }
stage('restart-httpd') {
steps {
         sh "service httpd restart"
            }
           }
            }
       }
                                    
