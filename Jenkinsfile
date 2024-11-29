pipeline {
    agent any

    parameters {
        choice(name: 'STAGES_TO_RUN', choices: 'checkout\nclean\ncompile\npackage')
    }

    stages {
        stage(' git checkout') {
            when {
                expression { params.STAGES_TO_RUN.contains('checkout') }
            }
            steps {
              git branch: 'master',
                url: 'https://github.com/Sunildevangam15/servlet.git'
            }
        }
        stage('clean') {
            when {
                expression { params.STAGES_TO_RUN.contains('clean') }
            }
            steps {
                sh 'mvn clean'
            }
        }
        stage('compile') {
            when {
                expression { params.STAGES_TO_RUN.contains('compile') }
            }
            steps {
                 sh 'mvn compile'
            }
        }
        // Repeat similarly for all 10 stages
        stage('package') {
            when {
                expression { params.STAGES_TO_RUN.contains('package') }
            }
            steps {
                 sh 'mvn package'
            }
        }
    }
}
