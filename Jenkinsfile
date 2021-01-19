node {
environment {
SONARQUBE_LOGIN = "b4e3a148df6648832e305f8dbf0102a447b2d6e3"
}
stage('SCM'){
 git 'https://github.com/OussamaINTI/gestionAgenceVoyage'
}

stage('Compile'){
def mvnHome = tool name: 'maven-3' , type: 'maven'
sh "${mvnHome}/bin/mvn package"
}

stage('SonarQube') {
  def mvnHome = tool name: 'maven-3' , type: 'maven'
  sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url=http://192.168.1.11:9000/ -Dsonar.login=$SONARQUBE_LOGIN"
    }
}
