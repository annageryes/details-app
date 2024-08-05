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
       stage('pre-requisites'){
            steps{
                echo 'Checking pre-requisites'
                sleep "${sleep_time}"
                sh'''
                    export PATH=$PATH:~/.local/bin
                    sudo apt-get update
                    sudo apt-get install -y curl python3 pylint codespell virtualenv
                    virtualenv venv 
                    . venv/bin/activate 
                    pip install -r requirements.txt

           

                '''
            }
        }
        }  stage('trigger_spell_check_pipline'){
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
            } //

         stage('trigger_build_check_pipline'){
         
            steps{
                build job: 'details_app_build', wait: true, parameters: job_params
           
        }
        }
    
    }

  
}


