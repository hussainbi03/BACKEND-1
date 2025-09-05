pipeline {
    agent { label 'AGENT-1' }
    environment {
        PROJECT = 'expense'
        COMPONENT = 'backend'
        appVersion = ''
        ACC_ID = '052893174146'
    }
    options {
        disableConcurrentBuilds()
        timeout(time : 30, unit: 'MINUTES')
    }
   /*  // parameters{
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    } */
        stages {
            stage ('read version') {
                steps {
                    script {
                       
                             def packageJson = readJSON file: 'package.json'
                             appVersion = packageJson.version
                             echo "Version is: $appVersion"
                          
                    }
                }
            }
            stage ('install dependencies') {
                steps {
                    script {
                        sh """
                            npm install
                         """   
                    }
                }
            }
            stage ('deploy') {
               /*  input {
                    message "should we contunue?"
                    ok "yes, we can"
                    submitter "alice, bob"
                } */
               /*  when {
                    environment name: 'DEPLOY_TO', value: 'production'
                } */
                steps{
                    script {
                        sh """
                            echo "Hello, this is deploy"
                         """   
                    }
                }
            }
        
        }
    
        post {
            always{
                echo "I'll always say hello again"
            }
            success {
                echo "Pipeline is success"
            }
            failure {
                echo "Pipeline is failed"
            }
        }
}

    
