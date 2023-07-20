pipeline{
  agent {
    label 'slave-1'
  }
    stages{
      stage('stage-3'){
        steps{
          //sh "docker pull httpd"
        //  sh "sudo docker stop 23Q3-v"
         //sh "sudo docker rm 23Q3-v"
          sh "sudo docker system prune -a -f"
          sh "sudo docker run -itdv /mnt:/usr/local/apache2/htdocs/ httpd"
          sh "sudo docker run -itdp 8007:80 --name 23Q3-vs httpd"
          sh "sudo docker cp index.html 23Q3-vs:/usr/local/apache2/htdocs"
          sh "sudo docker exec 23Q3-vs chmod -R 777 /usr/local/apache2/"
        }
        
        
      }
    }
  }
