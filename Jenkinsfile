pipeline {
    agent any
        tools {nodejs "NodeJS"}
    stages {
	stage('Test') {
	    steps {
	       echo 'Run testing'
	       sh 'npm run test'
	       
	    }
	}
    }
    post {
      always {
         echo 'Finish'
      }
      Sucess {
         echo 'Everything OK'
         emailext attachLog: true,
             to: mateo7413@gmail.com, subject: 'Test failed!!!'
             subject: "Jenkinsfile test succeed!!"
      }
      failure {
          emailext attachLog: true,
             to: mateo7413@gmail.com, subject: 'Test failed!!!'
             subject: "Jenkinsfile test failed!!"
      }    
    }           
}
