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
          sh "mvn sonar:sonar -Dsonar.projectKey=studentproject -Dsonar.host.url=http://52.3.235.41:9000 Dsonar.login=b"
        }

    }
}
