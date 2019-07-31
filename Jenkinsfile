import org.jenkinsci.plugins.workflow.steps.FlowInterruptedException
pipeline {

	agent none
	environment {
	    MyKeyID="myCustomValue1"
	}
	
	stages {
	
stage("stage master") {
		steps {
    			script {
					stage("inner stage 1") {
						script {
							node {
								println "inner stage"
							}
						}
					}
					stage("inner stage 2") {
						script {
							node {
								println "inner stage"
							}		
						}
					}
                    }
				}
		}

	stage('Descargar codigo fuente') {
	    environment {
    	    MyKeyID="myCustomValue2x"
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
        			println "Mi segundo stage esta en ejecucion. KeyID: $MyKeyID"
          		}
        	}
    	}
	}
	
	stage('input Test') {
    	steps {
    		script {
    		    try {
    		        input (message: " esta seguro?")
    		    }
    		    catch(exc){
    		    }
    		    finally {
          	        node {
        			    println "iniciando deploy"
          		    }
    		       }
    		    }
    		    }
    }

	stage('Fin') {
    	steps {
    		script {
          		node {
        			println "Mi segundo stage esta en ejecucion. KeyID: $MyKeyID"
          		}
        	}
    	}
	}
}
}	    
