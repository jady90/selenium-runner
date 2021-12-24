pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				bat "docker pull jadyjdjady1990/selenium-docker"
			}
		}
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up search-module book-flight-module"
			}
		}
	}
	post{
		always{
		    archiveArtifacts artifacts: "C:\mydockerdata\slavejenkins\workspace\SELENIUM_RUNNER\Output"
			bat "docker-compose down"
		}
	}
}
