
pipeline {
	options {
      timeout(time: 1, unit: 'HOURS') 
      buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '30'))
  }
    agent any
	 stages {
           stage('Build') {
		       steps {
			

	//mavenProperties '-Dmaven.test.skip=true'

	enableFeatureBuild()
	enableDependencyRecommender()

	enableGitlabTrigger()
	enableCronTrigger('H 20 * * *')

	nonReleaseGoal = 'clean deploy --update-snapshots --threads 1.0C'
		       }
	       }
	 }
}



