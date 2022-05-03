pipeline {
    agent any
    parameters {
        choice(
            choices: ['maven' , 'gradle'],
            description: '',
            name: 'tool-id')
    }

    stages {
        stage ('maven_build') {
            when {
                
                expression { params.tool-id == 'maven' }
            }
            steps {
                mvn install
            }
        }
	stage ('gradle_build'){
		when {
		expression {params.tool-id == 'gradle'}	
		}
		steps{
		chmod +x ./gradlew
		./gradlew build
		}
	}
    }
}
