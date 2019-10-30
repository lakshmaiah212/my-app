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
          sh "${mvnHome}/bin/mvn sonar:sonar"
        }

    }
}
