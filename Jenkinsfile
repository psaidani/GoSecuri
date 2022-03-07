node {
    stage('Cloner') {
        git branch: 'main', url: 'https://github.com/psaidani/GoSecuri.git'
    }
    stage('Lire liste fichiers') {
        sh 'ls'
    }
    stage('Copier vers le serveur web') {
        sh 'cp go-securi/src/main/java/com/epsi/*  /var/www/html/'
        sh 'cp go-securi/src/test/java/com/epsi/*  /var/www/html/'
    }
    stage('Générateur') {
        steps {
		  echo 'Generate the application...'
          updateGitlabCommitStatus name: 'generation', state: 'pending'
          sh 'java -jar target/gosecuri-0-jar-with-dependencies.jar'
          updateGitlabCommitStatus name: 'generation', state: 'success'
        }
    }
}
