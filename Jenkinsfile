node {
   stage('Preparation') {
      parallel Tools: {
        echo 'Install/Check Tools'
        sleep 10
      }, Git: {
        echo 'Git clone/fetch'
        sleep 5
      }
   }
   stage('Build') {
      echo 'Build Binaries'
      sleep 15
   }
   stage('Tests') {
      parallel JUnit: {
        echo 'JUnit Test'
        sleep 6
      }, Sonar: {
        echo 'Sonar Check'
        sleep 10
      }, Dependencies: {
        echo 'Dependecies Check'
        sleep 4
      }
   }
   stage('Results') {
      parallel Reports: {
        echo 'Generate Test Reports'
        sleep 3
      }, Archive: {
        echo 'Archive artefacts'
        sleep 5
      }
   }
}
