node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/Lowens1996/JenkinsDemo'
      // Get the Maven tool.
      // ** NOTE: This '3.5.2' Maven tool must be configured
      // **       in the global configuration.
      mvnHome = tool '3.5.2'
   }
   stage('Build') {
      // Run the maven build
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
   }
}
