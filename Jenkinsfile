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
      stage ('download the package') {
        steps {
          sh 'sudo cp ${WORKSPACE}/target/spring-petclinic-3.0.0-SNAPSHOT.jar /home/ubuntu/spc'
          }
    }
      stage ('deploy the artifact') {
        steps {
          sh ' ansible-playbook -i host spc.yaml'
        }
      }
  }
}
