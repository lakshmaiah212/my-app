node {
    stage('SCM checkout'){
        git 'https://github.com/lakshmaiah212/my-app.git'
    }
    stage('compile-package'){
        def mavenhome = tool name: 'maven', type: 'maven'
        sh "${mavenhome}/bin/mvn package"
    }
}
