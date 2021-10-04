node(maven) {

   stage('SCM') {
      // git clone
	  git 'https://github.com/openmrs/openmrs-core.git'
   }
   
   stage ('build the packages') {
      // mvn package
	  sh 'mvn package'
   }
   
   stage('SonarQube analysis') {
    // performing sonarqube analysis with "withSonarQubeENV(<Name of Server configured in Jenkins>)"
    withSonarQubeEnv('SONAR-6.7.4') {
      // requires SonarQube Scanner for Maven 3.2+
      sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
    }
  }
   
   
}
