pipeline{
  agent any

  tools {
	nodejs "node18"
  }

  stages {
	
	stage('Checkout') {
	   steps{
		echo "Cloning repository..."
		checkout scm
	    }
	}

	stage('Install Dependencies'){
	   steps{
		echo"Running npm install..."
		sh 'npm install'
	}
 	}

	stage('Run Test'){
	   steps{
		echo "Running npm test..."
		sh 'npm test'
		}
	}

	stage ('Archive Artifacts') {
		steps{
		   echo "archiving logs and artifacts..."
		   archiveArtifacts artifacts: '**/npm-debug/log', fingerprint:true, allowEmptyArchive:true
	}
}
}
}
		
