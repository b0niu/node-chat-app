pipeline {
    agent any
        tools {nodejs "node"}
    stages {
	stage('Test') {
	    steps {
	       echo 'Run testing'
	       sh 'npm install'
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
             body: "Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}: ${currentBuild.currentResult}",
             to: 'mateo7413@gmail.com', 
             subject: "Jenkinsfile test succeed!!"
      }
      failure {
          emailext attachLog: true,
             body: "Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}: ${currentBuild.currentResult}",
             to: 'mateo7413@gmail.com', 
             subject: "Jenkinsfile test failed!!"
      }    
    }           
}
