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
      stage ('Create textfile'){
            steps{
               timestamps{
                  logstash{
              powershell "New-Item -Path 'file.txt' -ItemType File "
                  }
               }
            }     
      }  
      stage ('Add content to the file text'){
            steps{
               timestamps{
                  logstash{
              powershell "Set-Content file.txt 'Succesful Pipeline!, Check your logs on Elastic.'"
                  }
               }
            }     
      } 
      stage ('Move file to folder'){
           steps {
              timestamps{
                  logstash{
             powershell "Move-Item file.txt Backup"
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
      stage ('Move Backup Zip'){
           steps {
              timestamps{
                  logstash{
             powershell "Move-Item backup.gz Important"
                  }
              }
           }
      }
   }
}
