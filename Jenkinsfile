pipeline{
    agent any

    stages {

            stage ('Checkout'){
                    steps    {
                             echo "Running Checkout Phase"
                             git 'https://github.com/Imranonline/gradle-build-scan-quickstart.git'
                    }

            }

            stage ('Build') {
                steps{
                    sh './gradlew build --scan'
                }
            }

            stage ('Test') {
                steps {
                    echo 'Testing the stage completed see results '
                }
            }

                stage ('Deploy') {
                    when {
                        branch 'master'
                    }
                    input {
                message "Deploy to Prod ?"
                ok "Yes, we should."
                submitter "admin,imran"
                parameters {
                    string(name: 'COMMENT', defaultValue: 'Merged PR to Master', description: 'I have Merged the PR to Master')
                }
            }
                    
                steps {
                    echo 'Testing the stage completed see results '
                }
            }

    }


}
