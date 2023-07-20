pipeline{
  agent any
    stages{
      stage('stage-2'){
        steps{
         // sh "docker pull httpd"
          //sh "docker stop 23Q1-v"
         // sh "docker rm 23Q1-v"
          sh "docker system prune -a -f"
          sh "docker run -itdv /mnt:/usr/local/htdocs/"
          sh "docker run -itdp 80:80 --name 23Q2-v httpd"
          sh "docker cp index.html 23Q2-v:/usr/local/htdocs"
          sh "docker exec 23Q2-v chmod -R 777 /usr/local/htdocs/"
        }
        
        
      }
    }
  }
