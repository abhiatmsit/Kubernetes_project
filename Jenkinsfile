pipeline{
  agent any
  stages {
    stage ("builds"){
      steps{
        echo "building the application"
      }
    }
    stage ("test"){
      steps{
        echo "testing the application"
      }
    post {
    	
		success {
			echo "testing application is working"
		}
	}
    }
    stage ("deploy"){
      steps {
        echo "deploying the application"
        sh "uptime"
        sh "ps"
      }
  post {
    always{
      echo "application build,deploy and test is successfull"
    }
    failure{
      echo "application build deploy and test is unsuccessfull"
    }
    success{
      echo "Application build, deploy have been  successfull"
    }
  }  
    }
  }
}
