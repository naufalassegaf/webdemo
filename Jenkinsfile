pipeline {
    agent any

    stages {
        stage('Code') {
            steps {
                echo 'This stage is pulling the code'
            }
        }

        stage('Build') {
            steps {
                echo 'This stage is compiling the code'
            }
        }

        stage('Test') {
            steps {
                echo 'This stage is testing the compiled code result'
            }
        }

        stage('Release') {
            steps {
                echo 'This stage is releasing the artifact'
		sh 'copy "C:\ProgramData\Jenkins\.jenkins\workspace\Web Demo\index.html" "C:\Program Files\Apache Software Foundation\Tomcat 10.1\webapps\examples" '
            }
        }
    }
}