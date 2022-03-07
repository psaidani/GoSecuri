node {
    stage('Cloner') {
        git branch: 'main', url: 'https://github.com/psaidani/GoSecuri.git'
    }
    stage('Lire liste fichiers') {
        sh 'ls'
    }
    stage('Copier vers le serveur web') {
        sh 'cp go-securi/src/main/java/com/epsi/*  /var/www/html/'
    }
}
