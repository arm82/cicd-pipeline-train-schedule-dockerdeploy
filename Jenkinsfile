#!/usr/bin/env groovy

timeout = 60
	numberOfBuildsToKeep = 10

	enableFeatureBuild()
	enableDependencyRecommender()

	enableGitlabTrigger()
	enableCronTrigger('H 20 * * *')

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
    }
}
