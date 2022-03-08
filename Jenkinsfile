node {
    stage('Cloner') {
        git branch: 'main', url: 'https://github.com/psaidani/GoSecuri.git'
    }
    stage('Lire liste fichiers') {
        sh 'ls'
    }
    
    stage('Compilation JAR') {
        sh 'cd /var/www/html/; mvn clean install'
    }
    stage('Copier vers le serveur web') {
        sh 'pwd'
        sh 'mv -r ./*  /var/www/html/'
    }
    stage('Générateur') {
    	sh 'java -jar target/gosecuri-0-jar-with-dependencies.jar'
        
    }
}
