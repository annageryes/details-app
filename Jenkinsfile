pipeline{
    agent {label 'workers'}

    stages{
        
        stage('main_pipline'){
            steps{
                echo 'statring main pipline'
            } //error with artifact
        }
        stage('trigger_spell_check_pipline'){
            steps{
                build job: 'spellcheck', wait: true
            } //error with artifact
        }
    }
}


