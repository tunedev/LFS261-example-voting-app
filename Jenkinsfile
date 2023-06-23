pipeline{
	agent any
	
	stages {
		stage("hello"){
			steps {
				echo 'Hello world'
			}
		}
	}
	post{
		always{
			echo "This pipeline is completed"
		}
		failure{
			slackSend (channel: "#ci-cd", message: "Build Failure: ${env.JOB_NAME} ${env.BUILD_NUMBER}")
		}
		success{
			slackSend (channel: "#ci-cd", message: "Build Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}")
		}
	}
}
