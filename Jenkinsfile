pipeline {
    agent any
    parameters {
        choice(
            choices: ['maven' , 'gradle'],
            description: '',
            name: 'tool_id')
    }

    stages {
        stage ('maven_build') {
            when {
                
                expression { params.tool_id == 'maven' }
            }
            steps {
                sh './mvnw package'
            }
        }
	stage ('gradle_build'){
		when {
		expression {params.tool_id == 'gradle'}	
		}
		steps{
		sh 'chmod +x ./gradlew'
		sh '/gradlew build'
		}
	}
    }
}
