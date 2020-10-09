pipeline {
  agent any
  tools {
      maven 'M2_HOME'
  }
  stages {
    stage ('build'){
      steps {
        echo "Build step" 
        sh 'mvn clean'
        sh 'mvn install'
        sh 'mvn package'
     }
   
      
    }
     stage ('test'){
      steps {
        echo "test stage" 
        sh 'mvn test'
     }
   
       
    }
     stage ('deploy'){
      steps {
        
        deploy adapters: [tomcat8(credentialsId: 'TomcatID', path: '', url: 'http://18.221.100.182:8080/')], contextPath: null, war: '**/*.war'
     }
   
       
    }
    
 }
  
} 
post {
  alway {
      echo "alwaya display this mesage"
  }
  failure {
    echo "job failed "
  }
  success {
    echo "Successful run "
  }
  unstable {
    echo "The job is unstable "
   }
}
      
