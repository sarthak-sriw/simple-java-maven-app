pipeline{
    
    agent none
   
    stages{
        
        stage('Build'){
            
            agent{
                label 'myslavenode'
            }
            
            steps {
                echo "build master branch"
                sh 'ls -l'   
            }
        }
        
    }
}
