pipeline {
  agent any
  stages {
    stage('Launch infrastructure') {
      steps {
        sh 'terraform init'
        sh 'terraform plan'
        sh 'terrraform apply --auto-approve'
      }
    }

    stage('Building Docker image') {
      steps {
        sh 'docker build . -t my-flaskapp-image:1.0.1'
      }
    }

    stage('Pushing image') {
      steps {
        sh 'docker push drestrepor/project-lab_demo1:appdemo'
      }
    }

  }
}