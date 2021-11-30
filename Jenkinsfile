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
				  sh '/home/jendemo/sftware/apache-tomcat-9.0.54/bin/startup.sh'
                                  echo "Files Deployed successfully"
                                  }
                      }
              }
}
