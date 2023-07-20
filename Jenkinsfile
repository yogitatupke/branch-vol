pipeline{
  agent {
    label 'slave-1'
  }
    stages{
      stage('stage-2'){
        steps{
          //sh "docker pull httpd"
         sh "sudo docker stop 23Q2-vs"
          sh "sudo docker rm 23Q2-vs"
          sh "sudo docker system prune -a -f"
          sh "sudo docker run -itdv /mnt:/usr/local/apache2/htdocs/ httpd"
          sh "sudo docker run -itdp 8006:80 --name 23Q2-vs httpd"
          sh "sudo docker cp index.html 23Q2-vs:/usr/local/apache2/htdocs"
          sh "sudo docker exec 23Q2-vs chmod -R 777 /usr/local/apache2/"
        }
        
        
      }
    }
  }
