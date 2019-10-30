node{
    stage('scm-checkout'){
        git "https://github.com/lakshmaiah212/my-app.git"
    }
    stage('compile-package'){
        def mavenhome = tool name: 'maven', type: 'maven'
        sh "${mavenhome}/bin/mvn package"
    }
    stage('Sonar Qube Analysis'){
         def mavenhome = tool name: 'maven', type: 'maven'
         withSonarQubeEnv('sonar-8') { 
          sh "mvn sonar:sonar -Dsonar.projectKey=studentproject -Dsonar.host.url=http://52.3.235.41:9000 Dsonar.login=dd40413f0bc20b7c57c3f1d051647bb8be6643fb"
        }

    }
    stage("Quality Gate status check"){
          timeout(time: 1, unit: 'HOURS') {
              def qg = waitForQualityGate()
              if (qg.status != 'OK') {
                  error "Pipeline aborted due to quality gate failure: ${qg.status}"
              }
          }
      }        
}
