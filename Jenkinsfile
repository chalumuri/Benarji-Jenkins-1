
pipeline{
  
  agent any 
  
  parameters{
                 booleanParam(name: 'skipBuild',
                              defaultValue: false,
                              description: 'well, no description'
                              )
                choice(name: 'BuildOnly',
                       
                       choices: 'no\nyes'
                       )
  }

stages {
  stage('Build') {
    when {
      anyOf {
        expression { params.skipBuild == 'true'}
        expression { params.BuildOnly == 'yes'}
      }
    }
    steps{
           echo 'hellow world'
    }
  }
  stage('Test'){
    steps{
             echo "second world \$\(pwd\)"
            
             
    }
  }
}
}	
