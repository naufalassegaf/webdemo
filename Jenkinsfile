pipeline {
    agent any
      
      stages{
        stage('Install NGINX') {
            steps {
                echo 'Installing Nginx ...'
                sh '''
                   ssh NGINX sudo yum install nginx -y
                   ssh NGINX sudo systemctl enable nginx
                   ssh NGINX sudo systemctl start nginx
                '''
            }
        }

        stage('Check NGINX status') {
            steps {
                echo 'Checking Nginx service status...'
                sh 'ssh NGINX sudo systemctl status nginx'
                echo 'Checking Nginx HTTP response...'
                sh 'ssh NGINX sudo curl -I http://NGINX'
            }
        }	

        stage('Set Firewall for NGINX') {
            steps {
                echo 'Setting firewall for NGINX...'
                sh 'ssh NGINX sudo firewall-cmd --permanent --add-service=http'
                sh 'ssh NGINX sudo firewall-cmd --reload'
                sh 'ssh NGINX sudo firewall-cmd --list-all | grep services'
                echo 'Setting firewall is done...'
            }
        }

        stage('Change Home Page') {
            steps {
                echo 'Changing the Home page...'
                sh 'ssh NGINX sudo firewall-cmd --permanent --add-service=http'
                sh 'ssh NGINX sudo firewall-cmd --reload'
                sh 'ssh NGINX sudo firewall-cmd --list-all | grep services'
                echo 'Setting firewall is done...'
            }
        }
    }
}    