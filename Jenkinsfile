pipeline {
    agent any
    stages {
        stage ('Checkout SCM') {
               steps{
                   echo "Running Checkout Phase"
               }
        }

        stage ('Build') {
               
                steps{
                   echo "Running Build "
               }
        }

        stage ('Test') {
                steps{
                   echo "Running Testing Phase"
               }
        }

        stage ('Deploy') {
                steps{
                   echo "Deploying..."
                   
               }
        }
    }
}
