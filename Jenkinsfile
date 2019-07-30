pipeline {

	agent none

	options {
		buildDiscarder logRotator( daysToKeepStr: '8', numToKeepStr: '5') 
	}

	environment {
	    MyKeyID="myCustomValue1"
	}
	
	stages {

	stage('Descargar codigo fuente') {
		when {
			branch "master"
		}
    	steps {
    		script {
          		node {
        				println "\n Mi primer stage.\n MyKeyID value es: ${MyKeyID}\n"
          		}
        	}
    	}
	} 
	
	stage('Test') {
    	steps {
    		script {
          		node {
        				println "\nMi segundo stage esta en ejecucion. KeyID: $MyKeyID\n"
          		}
        	}
    	}
	}
}
}