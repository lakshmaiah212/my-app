node {
    stage('SCM checkout'){
        git 'https://github.com/lakshmaiah212/my-app.git'
    }
    stage('compile-package'){
        def mavenhome = tool name: 'maven', type: 'maven'
        sh "${mavenhome}/bin/mvn package"
    }
    stage('Email Notification'){
        mail bcc: '', body: 'thanks', cc: '', from: '', replyTo: '', subject: 'pipelinejob', to: 'lakshmaiah212@gmail.com'
    }
}
