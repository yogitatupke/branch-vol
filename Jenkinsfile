pipeline{
  agent any
    stages{
      stage('stage-3'){
        steps{
          //sh "docker pull httpd"
          //sh "docker stop 23Q3-v"
         // sh "docker rm 23Q3-v"
          sh "docker system prune -a -f"
          sh "docker run -itdv /mnt:/usr/local/apache2/htdocs/"
          sh "docker run -itdp 8000:80 --name 23Q3-v httpd"
          sh "docker cp index.html 23Q3-v:/usr/local/apache2/htdocs"
          sh "docker exec 23Q3-v chmod -R 777 /usr/local/apache2/"
        }
        
        
      }
    }
  }
