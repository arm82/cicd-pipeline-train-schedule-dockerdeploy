
pipeline {
	options {
      timeout(time: 1, unit: 'HOURS') 
      buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '30'))
  }
    agent any
	 stages {
           stage('Build') {
		       steps {
		
			      
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
          

	//mavenProperties '-Dmaven.test.skip=true'

	enableFeatureBuild()
	enableDependencyRecommender()

	enableGitlabTrigger()
	enableCronTrigger('H 20 * * *')

	sh 'clean deploy --update-snapshots'
		       }
	       }
	 }
}



