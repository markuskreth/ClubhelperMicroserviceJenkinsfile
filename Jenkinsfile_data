node {
    def mvnHome = tool 'M3'
    dir('clubhelper-data') {
    	stage('clubhelper-data') {
	    	pwd()
		    stage('Checkout data') {
		    	cleanWs()
		        git branch: 'master', credentialsId: 'github_markus_password', url: 'https://github.com/markuskreth/clubhelper-data.git'
		    }
		    stage('Build data') {
		        sh "${mvnHome}/bin/mvn clean install"
		    }
    	}
	}
}
