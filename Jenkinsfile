pipeline {
    agent any

    stages {
        stage('Cloning') {
            steps {
                echo 'cloning doing'
git credentialsId: 'santhu', url: 'https://github.com/wakaleo/game-of-life.git'
}
}
        stage('mvn') {
            steps {
                echo 'mvn doing'
sh 'mvn clean install'
} 
}
stage('tomcat') {
            steps {
                echo 'tomcat doing'
deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://174.129.83.58:8080/')], contextPath: 'batch7new', war: '**/*war'
} 
}
}
}
