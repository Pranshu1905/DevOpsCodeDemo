
pipeline{
    tools{
       
        maven 'mymaven'
    }
	agent any
      stages{
           stage('Checkout the code'){
	    
               steps{
		 echo 'cloning the repo'
                 git 'https://github.com/Pranshu1905/DevOpsCodeDemo.git'
              }
          }
          stage('Compile'){
             
              steps{
                  echo 'complie the code again..'
                  sh 'mvn compile'
	      }
          }
          stage('CodeReview'){
		  
              steps{
		    
		  echo 'codeReview'
                  sh 'mvn pmd:pmd'
              }
          }
           stage('UnitTest'){
		  
              steps{
	         
                  sh 'mvn test'
              }
          
          }
        
          stage('Package'){
		  
              steps{
		  
                  sh 'mvn package'
              }
          }
stage('Deploy Code in tomcat')
  {
    steps{
     deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'fdfa0e09-4ae1-4a89-8808-b2f8992422ad', path: '', url: '')], contextPath: null, war: '**/*.war'
   }
  }
}

  
}
