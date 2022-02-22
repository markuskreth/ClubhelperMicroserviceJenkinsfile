node {
    def mvnHome = tool 'M3'
    stage('Checkout clubhelper-data') {
        git 'https://github.com/markuskreth/clubhelper-data.git'
    }
    stage('Build clubhelper-data') {
        sh "${mvnHome}/bin/mvn clean install"
    }
}