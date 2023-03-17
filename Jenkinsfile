pipeline {
  agent { node { label 'node_all' } }
  stages {
      stage ('git') {
        steps {
          git url: 'https://github.com/spring-projects/spring-petclinic.git',
          branch: 'main'
      }
      }
      stage ('build') {
        steps {
          sh './mvnw package'
      }
    }
  }
}
