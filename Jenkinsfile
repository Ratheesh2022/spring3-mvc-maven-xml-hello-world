pipeline {
agent any
      
   stages {
        stage ('SCM') {
            steps {
                 git credentialsId: 'github_credentials', url: 'https://github.com/Ratheesh1986/spring3-mvc-maven-xml-hello-world.git'
                }
           }
        stage ('Build') {
            steps {
                 sh "mvn -Dmaven.test.failure.ignore=true clean package"
                }
           }
           
        stage ('Artifacts') {
            steps {
                
                 archiveArtifacts 'target/*.war'
                }
           }
         
        stage('deploy') {
            steps {
                // Tomcat deploy
                    
                    sh "curl -v -u admin:adminadmin -T /var/lib/jenkins/workspace/spring3123/target/spring3-mvc-maven-xml-hello-world-1.0-SNAPSHOT.war 'http://13.232.213.211:8080/manager/text/deploy?path=/kerala&update=true'"
                              
               }    
           
            
           } 
         
        }

    
   }
