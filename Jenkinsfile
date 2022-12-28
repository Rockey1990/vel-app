pipeline {
      agent {
              label {
                       label 'built-in'
                       customWorkspace "/data/project"
                    }
            }
stages {
          stage ('install git') {
          steps {
                 sh "yum install httpd -y"
                }
            }
      stage ('start-httpd') {
            steps {
                   sh "service httpd start"
            }
      }
        stage ('copy-index') {
        steps {
                sh "cp -r /mnt/vel-app/index.html /var/www/html/index.html"
                sh "chmod -R 777 /var/www/html/index.html"
                   }
              }
         stage ('restart-httpd') {
           steps {
                   sh "service httpd restart"
                }
              }
         }
    }

