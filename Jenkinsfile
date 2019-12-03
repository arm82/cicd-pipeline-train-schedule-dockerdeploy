
pipeline {
	options {
      timeout(time: 1, unit: 'HOURS') 
  }
    agent any
	 stages {
           stage('Build') {
		       steps {
			

	//mavenProperties '-Dmaven.test.skip=true'

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



