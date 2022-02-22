node {
    def mvnHome = tool 'M3'
    dir('clubhelper-data') {
	    stage('Checkout data') {
	    	cleanWs()
	        git branch: 'master', credentialsId: 'github_markus_password', url: 'https://github.com/markuskreth/clubhelper-data.git'
	    }
	    stage('Build data') {
	        sh "${mvnHome}/bin/mvn clean install"
	    }
	}
    dir('vaadin-components') {
	    stage('Checkout vaadin-components') {
	        git branch: 'master', credentialsId: 'github_markus_password', url: 'https://github.com/markuskreth/clubhelper-vaadin-components.git'
	    }
	    stage('Build vaadin-components') {
	        sh "${mvnHome}/bin/mvn clean install"
	    }
    }
    dir('backend') {
	    stage('Checkout backend') {
	    	cleanWs()
	        git branch: 'master', credentialsId: 'github_markus_password', url: 'https://github.com/markuskreth/clubhelper_backend_model.git'
	    }
	    stage('Build backend') {
	        sh "${mvnHome}/bin/mvn -DskipTests clean install spring-boot:build-image -Dspring-boot.build-image.imageName=markuskreth/clubhelperrest"
	    }
	    stage('Build backend image') {
	        sh "${mvnHome}/bin/mvn -DskipTests spring-boot:build-image -Dspring-boot.build-image.imageName=markuskreth/clubhelperrest"
	    }
	//    stage('Create Docker image backend') {
	//    	sh "java -Djarmode=layertools -jar target/ClubhelperModel*.jar list"
	//    }
	//    stage('Install Docker image backend') {
	//        docker build --tag markuskreth/clubhelperrest .
	//    }
    }
}
