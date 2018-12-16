#! groovy
node{

  /* stage('checkout'){
       git credentialsId: 'b5870b31-115f-47a9-b11d-5ca1d9ab938a', url: 'https://github.com/DevopsMT/maven-web-application.git'
   }*/
   stage('Checkout'){

     checkout scm
     }
 
   stage('install')

    {

      def mvn_version = 'maven-3.6.0'

       withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] )

          {         
		  sh 'mvn clean install'

          }   
	  }

   stage('deploy')

    {

      def mvn_version = 'maven-3.6.0'

       withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] )

          {         
		  sh 'mvn clean deploy'
           }   
	 }

  /* stage('sonar')

    {

      def mvn_version = 'maven-3.6.0'

       withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] )

          {         
		  sh 'mvn sonar:sonar '

          }   
     }*/

  }
