pipeline{
  agent any
  stages {
    when {
      expression {
        BRANCH_NAME=="main" && CODE_CHANGES==true
      }
    }
    stage ("builds"){
      steps{
        echo "building the application"
      }
    }
    stage ("test"){
      steps{
        echo "testing the application"
      }
      post('test') {
        echo "test is successful"
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
      echo "application build,deploy and test is successfule"
    }
    failure{
      echo "application build deploy and test is unsuccessfull"
    }
    success{
      echo "just printing the success message"
    }
  }  
    }
  }
}
