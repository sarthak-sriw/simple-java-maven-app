pipeline{
    
    agent none
    
    parameters {
        string(name: 'X',defaultValue: 'sriw',description:'your name')
    }
    
    stages{
        
        stage('Build'){
            
            agent{
                label 'myslavenode'
            }
            
            steps {
                echo "${params.X}"
                git 'https://github.com/sarthak-sriw/simple-java-maven-app.git'
                sh 'ls -l'
                sh 'pwd'
                stash includes: "pom.xml" , name:'myapp'
                
            }
        }
        
        stage('Testing'){
            agent{
                label 'myslavenode'
            }
            
            steps {
                echo "test............"  
                unstash 'myapp'
                sh 'mvn package'
                stash includes: 'target/*.jar',name:'jarfile'
            }
        }
        
        stage('Deploy'){
            agent{
                label 'myslavenode'
            }
             
            steps {
                echo "deploy............."  
                unstash 'jarfile'
                sh 'java -jar *.jar'
            }
        }
    }
}
