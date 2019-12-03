
pipeline {
    agent any
	 stages {
           stage('Build') {
		       steps {
			

	//mavenProperties '-Dmaven.test.skip=true'

	timeout = 60
	numberOfBuildsToKeep = 10

	enableFeatureBuild()
	enableDependencyRecommender()

	enableGitlabTrigger()
	enableCronTrigger('H 20 * * *')

	nonReleaseGoal = 'clean deploy --update-snapshots --threads 1.0C'
		       }
	       }
	 }
}



