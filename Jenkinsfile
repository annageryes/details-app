pipeline{
    agent {label 'worker'}

    stages{
        
        stage('main_pipline'){
            steps{
                echo 'statring main pipline'
            } //error with artifact
        }
        stage('pre-requisits'){
            steps{
                echo 'pip install codespell'
            } //error with artifact
        }
        yum install spellcheck
        stage('trigger_spell_check_pipline'){
            steps{
                build job: 'spellcheck', wait: false
            } //error with artifact
        }
    }
}


