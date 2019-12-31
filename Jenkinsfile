pipeline{
   agent any
   stages {
       stage ('Create folder'){
            steps{
              powershell "mkdir Important"
              powershell "mkdir Backup"
            }     
      }
      stage ('Copy file to folder'){
           steps {
             powershell "cp file.txt Backup"
           }
      }
      stage ('Zip Backup'){
           steps {
             powershell "tar -zcvf backup.gz Backup"
           }
      }
      stage ('Delete Backup folder'){
           steps {
             powershell "rm -r Backup"
           }
      }
   }
}
