pipeline {
    agent any

    stages {
        
        
           stage('w/o docker') {
            steps {
               sh'''
               echo "Without docker"
               mkdir -p build
               touch build/demo.txt
               ls -la
               '''
            }
        }
        
         stage('with docker'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            
            steps{
                sh''' 
                npm --version
                node --version
                mkdir -p build
               touch build/demo2.txt
               ls -la
                '''
            }
        }
        
     
        
       
    }
}
