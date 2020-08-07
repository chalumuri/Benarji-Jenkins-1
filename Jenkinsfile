
pipeline{
  
  agent any 
  
  parameters{
                 booleanParam(name: 'skipBuild',
                              defaultValue: false,
                              description: "well, no description"
                              )
  }

stages {
  stage('Build') {
    when {
      anyOf {
        expression { params.skipBuild == 'yes'}
      }
    }
    steps{
           echo 'hellow world'
    }
  }
  stage('Test'){
    steps{
             echo "second world"
    }
  }
}
}	
