node("slave1") {
  gradleHome = tool 'gradle4'
  try{
    stage ("Checkout"){
      checkout scm
    }
    stage ("build"){
      sh ${gradleHome}/bin/gradle 'build'
    }
  }
  catch (ex){
    echo "Error has occured!"
  }
  post {
    if (currentBuild.result == 'SUCCESS'){
      addBadge(icon: 'success.gif', text: 'very good!')
    }else if (currentBuild.result == 'FAILURE'){
      addBadge(icon: 'error.gif', text: 'not very good!')
    }
  }
  
}
