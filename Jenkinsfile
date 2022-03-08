node {
    stage('Cloner') {
        git branch: 'main', url: 'https://github.com/psaidani/GoSecuri.git'
    }
    stage('Lire liste fichiers') {
        sh 'ls'
        sh 'ls /var/www/html/'
    }
    stage('Suppression vieux fichiers') {
        sh 'cd /var/www/html/; rm -rf *'
    }
    stage('Copier vers le serveur web') {
        sh 'pwd'
        sh 'mv ./*  /var/www/html/'
    }
    stage('Compilation JAR') {
        sh 'cd /var/www/html/; mvn clean install'
    }
    stage('Générateur') {
    	sh 'java -jar /var/www/html/target/go-securi-1.jar'
        
    }
}
