pipeline{
    agent {label 'workers'}

    stages{
        
        stage('spellcheck'){
            steps{
                echo 'check code spell check'
                sleep 2
                sh '''
	            echo "spellcheck"
                    #codespell /home/jenkins/
                '''
            } //error with artifact
        }
    }
}


