node {
    stage('Cloner') {
        git branch: 'main', url: 'https://github.com/psaidani/GoSecuri.git'
    }
    stage('Lire liste fichiers') {
        sh 'ls'
        sh 'ls /var/www/html/'
    }
    stage('Suppression vieux fichiers') {
        sh 'rm -rvf /var/www/html/go-securi'
    }
    
    stage('Compilation JAR') {
        sh 'cd /var/www/html/; mvn clean install'
    }
    stage('Copier vers le serveur web') {
        sh 'pwd'
        sh 'mv ./*  /var/www/html/'
    }
    stage('Générateur') {
    	sh 'java -jar 1/go-securi-1.jar'
        
    }
}
