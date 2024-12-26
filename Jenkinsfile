pipline{
  agent any
  environment{
    PYTHON_PATH=''
  }
  stage{
    stage('checkout'){
      steps{
        checkout scm
      } 
    }
  }
  stage('build'){
    steps{
      bat '''
      set PATH =%PYTHON_PATH; %PATH%
      pip install -r requirment.txt
      '''
    }
  }
  stage('sonarqube-Analysis'){
    environment{
      SONAR-TOKEN=credentials()
    }
  }
}
