pipeline{
  agent any {
    label 'slave-1'
  }
    stages{
      stage('stage-1'){
        steps{
          sh "sudo docker pull httpd"
         //sh "docker stop 23Q1-v"
         //sh "docker rm 23Q1-v"
          sh "sudo docker system prune -a -f"
          sh "sudo docker run -itdv /mnt:/usr/local/apache2/htdocs/ httpd"
          sh "sudo docker run -itdp 8005:80 --name 23Q1-vs httpd"
          sh "sudo docker cp index.html 23Q1-vs:/usr/local/apache2/htdocs"
          sh "sudo docker exec 23Q1-vs chmod -R 777 /usr/local/apache2/"
        }
        
        
      }
    }
  }
