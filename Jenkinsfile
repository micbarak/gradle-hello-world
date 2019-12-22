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
    echo "Erroe has occured!"
  }
  post {
    if (currentBuild.result == 'SUCCESS' || currentBuild.result == 'SUCCESS'){
      addBadge(icon: 'success.gif', text: 'very good!')
    }else{
      addBadge(icon: 'error.gif', text: 'not very good!')
    }
  }
  
}
