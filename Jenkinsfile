


pipeline{
    agent any
    parameters {
        booleanParam(name: 'skipScans',
                defaultValue: false,
                description: 'Enable this to skip scans, scans cant be skipped for tag')
        choice(name: 'scanOnly',
                choices: 'no\nyes',
                description: 'This can be used to run scans . Just select yes and all leave all other parameters as no')
        choice(name: 'dockerPush',
                choices: 'no\nyes',
                description: 'Should image be pushed to docker ? this will trigger build and scan stages')
        choice(name: 'deploy',
                choices: 'no\nyes',
                description: 'Should image be deployed to dev ?')
        choice(name: 'Promote to test',
                choices: 'no\nyes',
                description: 'Should iamge be promoted to test')
    }
    stages{
        stage('Build'){
            when {
                    anyOf {
                        expression { params.dockerPush == 'yes' }
                        expression { params.scanOnly == 'yes' }
                    }
                }
            steps{
                echo '*******Executing Build Step*******'
            }
        }
    }
