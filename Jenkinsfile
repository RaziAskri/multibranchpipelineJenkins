pipeline {

  agent any

  options {

    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')

  }

  stages {

    stage('Hello') {

      steps {

        sh '''

          java -version

        '''

      }

    }

    stage('cat README') {

      when {

        branch "dev-*"

      }

      steps {

        sh '''

          cat README.md

        '''

      }

    }

    stage('cat OPENME') {

      when {

        branch "ops-*"

      }

      steps {

        sh '''

          cat OPENME.md

        '''

      }

    }



    stage('open all files: master login') {

     when {

       branch "master"
     
     }

     steps {


       sh '''
         
         cat README.md
         cat OPENME.md

       '''

       }
}





  }

}
