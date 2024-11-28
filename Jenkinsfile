pipeline {
    agent any

    parameters {
        choice(name: 'STAGES_TO_RUN', choices: 'checkout,clean,compile,test,package', description: 'Enter the stages you want to run (comma-separated)')
    }

    stages {
        stage(' git checkout') {
            when {
                expression { params.STAGES_TO_RUN.contains('clone') }
            }
            steps {
              git https://github.com/Sunildevangam15/servlet.git
            }
        }
        stage('Stage 2') {
            when {
                expression { params.STAGES_TO_RUN.contains('Stage2') }
            }
            steps {
                echo 'Executing Stage 2'
            }
        }
        stage('Stage 3') {
            when {
                expression { params.STAGES_TO_RUN.contains('Stage3') }
            }
            steps {
                echo 'Executing Stage 3'
            }
        }
        // Repeat similarly for all 10 stages
        stage('Stage 10') {
            when {
                expression { params.STAGES_TO_RUN.contains('Stage10') }
            }
            steps {
                echo 'Executing Stage 10'
            }
        }
    }
}
