node {
        try {
            cleanWs()
            stage('Checkout') {
                // Pull the code from the repo
                
            checkout scm
            
                sh 'echo $BRANCH_NAME'

            if (env.BRANCH_NAME == 'master') {
    stage 'Only on master'
    println 'This happens only on master'
    } else {
    stage 'Other branches'
    println "Current branch ${env.BRANCH_NAME}"
    } 
    sh 'git branch -a'
    sh 'git branch -r'
            }
            
            

            stage('Environment') {
                sh 'printenv'
            }
            
            stage('ReleaseNotes')
            {
                dir ('TMOAndroidApp')
                {
                    //sh 'git fetch -a'
                    //sh 'git checkout master'
                    //sh 'git checkout releasee'
                    //sh 'git sync'
                sh 'git branch -a'
                 sh "changelog.sh master keerthi"
                echo "ReleaseNotes"
                }
                
            }


        
        } catch (ex) {
            currentBuild.result = "FAILED"
            throw ex
        } finally {
        //   slackBuildStatus(currentBuild.result)
        }
    }
