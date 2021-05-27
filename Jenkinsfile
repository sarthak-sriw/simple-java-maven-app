pipeline{
    
    agent none
   
    stages{
        
        stage('Build'){
            
            agent{
                label 'myslavenode'
            }
            
            steps {
                echo "build branch"
                sh 'ls -l'   
            }
        }
        
    }
}
