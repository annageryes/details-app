pipeline{
    agent {label 'workers'} // needs to have ssh agent
    parameters{
        string(name: 'sleep_time', defaultValue:'2', description:'time to sleep')
    }
   
    stages{
        
        stage('main_pipline'){
            steps{
                echo 'statring main pipline'
                sleep "${sleep_time}"
            } //error with artifact
        }
       stage('Pre-Build'){
            steps{
                echo 'Checking pre-requisites'
                sleep "${sleep_time}"
                sh'''
                    export PATH=$PATH:~/.local/bin
                    sudo apt-get update
                    sudo apt-get install -y curl python3 pylint codespell
                    python3 -m pip install pytest

                '''
            }
        }
        stage('trigger_spell_check_pipline'){
            steps{
                build job: 'spellcheck', wait: true
            } //error with artifact
        }

        stage('trigger_syntax_check_pipline'){
            steps{
                build job: 'syntaxcheck', wait: true
            } //error with artifact
        }

        stage('trigger_test_pipline'){
            steps{
                build job: 'details_app_test', wait: true
            } //error with artifact
        }

         stage('trigger_build_check_pipline'){
            steps{
                build job: 'details_app_build', wait: true
            } //error with artifact
        }
    
    }

  
}


