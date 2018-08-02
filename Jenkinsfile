node {
 	// Clean workspace before doing anything
    deleteDir()

    try {
        stage ('Sindhu') {
        	checkout scm
        }
        stage ('Anusha') {
        	sh "echo 'shell scripts to build project...'"
        }
        stage ('Deepika') {
	        parallel 'static': {
	            sh "echo 'shell scripts to run static tests...'"
	        },
	        'unit': {
	            sh "echo 'shell scripts to run unit tests...'"
	        },
	        'integration': {
	            sh "echo 'shell scripts to run integration tests...'"
	        }
        }
      	stage ('Anithax') {
            sh "echo 'shell scripts to deploy to server...'"
      	}
    } catch (err) {
        currentBuild.result = 'FAILED'
        throw err
    }
}
