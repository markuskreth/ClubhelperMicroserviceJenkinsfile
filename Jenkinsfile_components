node {
    def mvnHome = tool 'M3'
    dir('vaadin-components') {
    	pwd()
	    stage('Checkout vaadin-components') {
	        git branch: 'master', credentialsId: 'github_markus_password', url: 'https://github.com/markuskreth/clubhelper-vaadin-components.git'
	    }
	    stage('Build vaadin-components') {
	        sh "${mvnHome}/bin/mvn clean install"
	    }
    }
}
