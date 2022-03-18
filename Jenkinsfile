node
 {
  def mavenHome = tool name: 'maven3.8.2'
  stage('1-Clone') {
    git 'https://github.com/Landmark-Technologies/maven-web-application' 
  }
  stage('2-build') {
    sh "${mavenHome}/bin/mvn clean package"
  }
  stage('3-CodeQuality') {
   //sh "${mavenHome}/bin/mvn sonar:sonar"
  }
  stage('4-Nexus') {
    //sh "${mavenHome}/bin/mvn deploy"
  }
   stage('5-deployDocker') {
    sh "docker build -t image:1 . "
    sh "docker run --name web-app -d -p 7000:8080 image:1" 
   }

   stage('6-email') {
    //sh
   }
} 
