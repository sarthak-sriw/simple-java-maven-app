pipeline{
    
    agent none
   
    stages{
        
        stage('Build'){
            
            agent{
                label 'myslavenode'
            }
            
            steps {
                echo "build sar branch"
                sh 'ls -l'   
            }
        }
        
    }
}
