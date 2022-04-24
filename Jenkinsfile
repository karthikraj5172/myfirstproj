currentBuild.displayName = "Testingjob1-#"+currentBuild.number

pipeline
{
          agent any

              stages 
              {
                      stage ('Checkout') {
                            steps {
                                  echo "Checkout Completed Successfully"
                                  }
                      }
                      stage ('Approval Stage') {
                            steps {
                                  input "Does this release has all the approvals in place?"
                            }
                      }
                      stage ('Build Stage') {
                            steps {                       
                                  sh 'echo Build process started'
                                  sh 'mvn --version'
                                  sh 'mvn clean install'
                                  sh 'echo Build Completed'
                            }
                      }
                      stage ('Deployment Stage') {
                            steps {
				    sh 'cp $HOME/.jenkins/workspace/job1/target/demofinal.war $HOME/Tomcat/apache-tomcat-8.5.71/webapps' 
				    sh '$HOME/Tomcat/apache-tomcat-8.5.71/bin/startup.sh'
	                            echo "Files Deployed successfully"
                                  }
                      }
              }
}
