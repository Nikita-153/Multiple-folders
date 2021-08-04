def BUILD_STAGE = "false"
pipeline {
    agent any
    
    
    stages {
        stage('Check Out') {
            steps {
                
//                 // testing
//                 echo 'Checking out... GIT_COMMIT:'
//                 echo "${env.GIT_COMMIT}"
//                 echo "Files updated!!!"
                
                

              script {
                def checkPath = "folder1"
                def stdout = bat(returnStdout: true, script: 'git show --name-only --pretty=format:').split("\n")
                println("stdout value is:" + stdout) 
                print("Going Inside for")
                  
                  
                  for(int i = 2; i<stdout.length; i++ ){
                        println(stdout[i])
                      if(stdout[i].contains(checkPath)){
                        print("Congratulations!!!!!!!!!!!!!!!!!!! value is set to true")
                        BUILD_STAGE = "true"
                        break
                      }else{
                        print("Else otherwise value is set to true .................................:)")
                      }
                  }
                } // End of script
                
            } // End of step
        } // End of stage
        
        
         stage('Build') {
            steps {
                echo 'Building...'
            }
        }
         stage('Folder Build executing') {
          
            steps {
                script{
                  if(BUILD_STAGE.equalsIgnoreCase("true")){            
                    echo 'Folder Build executing'
                    }// End of if
                }// End of script

            }// End of steps


        }// End of test




         stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
