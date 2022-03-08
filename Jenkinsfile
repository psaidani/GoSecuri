node {
    stage('Cloner') {
        git branch: 'main', url: 'https://github.com/psaidani/GoSecuri.git'
    }
    stage('Lire liste fichiers') {
        sh 'ls'
    }
    stage('Copier vers le serveur web') {
        sh 'mv ./*  /var/www/html/'
    }
    stage('Compilation JAR') {
        sh 'cd /var/www/html/; mvn clean install'
    }
    stage('Générateur') {
    	sh 'java -jar target/gosecuri-0-jar-with-dependencies.jar'
        
    }
}
