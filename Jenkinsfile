pipeline{
   agent any
   stages {
       stage ('Create folder'){
            steps{
               timestamps{
                  logstash{
              powershell "mkdir Important"
              powershell "mkdir backup"
                  }
               }
            }     
      }
      stage ('Copy file to folder'){
           steps {
              timestamps{
                  logstash{
             powershell "cp file.txt backup"
                  }
              }
           }
      }
      stage ('Zip Backup'){
           steps {
              timestamps{
                  logstash{
             powershell "tar -zcvf backup.gz backup"
                  }
              }
           }
      }
      stage ('Delete Backup folder'){
           steps {
              timestamps{
                  logstash{
             powershell "rm -r backup"
                  }
              }
           }
      }
   }
}
