pipeline{
    agent {label 'worker1'}

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
        stage('trigger_spell_check_pipline'){
            steps{
                build job: 'spellcheck', wait: false
            } //error with artifact
        }
    }
}


