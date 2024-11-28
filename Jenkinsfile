pipeline {
    agent any

    parameters {
        choice(name: 'STAGES_TO_RUN', choices: 'checkout,clean,compile,package', description: 'Enter the stages you want to run')
    }

    stages {
        stage(' git checkout') {
            when {
                expression { params.STAGES_TO_RUN.contains('clone') }
            }
            steps {
              git branch: 'master',
                url: 'https://github.com/Sunildevangam15/servlet.git'
            }
        }
        stage('clean') {
            when {
                expression { params.STAGES_TO_RUN.contains('Stage2') }
            }
            steps {
                sh 'mvn clean'
            }
        }
        stage('compile') {
            when {
                expression { params.STAGES_TO_RUN.contains('Stage3') }
            }
            steps {
                 sh 'mvn compile'
            }
        }
        // Repeat similarly for all 10 stages
        stage('package') {
            when {
                expression { params.STAGES_TO_RUN.contains('Stage10') }
            }
            steps {
                 sh 'mvn package'
            }
        }
    }
}
