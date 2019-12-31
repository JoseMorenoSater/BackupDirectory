pipeline{
   agent any
   stages {
       stage ('Create Important folder'){
            steps{
               timestamps{
                  logstash{
              powershell "mkdir Important"
                  }
               }
            }     
      }
       stage ('Create Backcup folder'){
            steps{
               timestamps{
                  logstash{
              powershell "mkdir Backup"
                  }
               }
            }     
      }  
      stage ('Create file text'){
            steps{
               timestamps{
                  logstash{
              powershell "New-Item -Path 'file.txt' -ItemType File "
                  }
               }
            }     
      }   
      stage ('Copy file to folder'){
           steps {
              timestamps{
                  logstash{
             powershell "cp file.txt Backup"
                  }
              }
           }
      }
      stage ('Zip Backup'){
           steps {
              timestamps{
                  logstash{
             powershell "tar -zcvf backup.gz Backup"
                  }
              }
           }
      }
      stage ('Delete Backup folder'){
           steps {
              timestamps{
                  logstash{
             powershell "rm -r Backup"
                  }
              }
           }
      }
   }
}
