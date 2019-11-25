pipeline{

	agent any

	environment{

		mvnGoals = "clean install"

	}

	parameters{
		string(name: 'releaseVersion', defaultValue: '1.0.${BUILD_NUMBER}', description: 'Automaticlay jenkins will increment the version')
	}

	tools{

		maven 'maven-3.6.2'

	}

	triggers{
		pollSCM('H */4 * * 1-5')
	}

	stages{

		stage('cloning'){
			steps{
				git(url: 'https://github.com/venkatasykam/DevOpsWebApp.git', branch: 'web', credentialsId: 'jengit', poll: true)
			}
		}

		stage('mvn build'){
			steps{
				print 'run the maven build'
			}
		}

	}
}
