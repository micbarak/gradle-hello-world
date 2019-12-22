node {label "slave1"}{
  def gradleHome = tool 'gradle4'
  stage ("Checkout"){
    checkout scm
  }
  build ("build"){
    sh "${gradleHome}/bin/gradle 'build'
  }
  post {
    if (currentBuild.result == 'SUCCESS' || currentBuild.result == 'SUCCESS'){
      addBadge(icon: 'success.gif', text: 'very good!')
    }else{
      addBadge(icon: 'error.gif', text: 'not very good!')
    }
  }
  
}
