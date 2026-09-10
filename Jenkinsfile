pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo 'Building Docker Application'
                bat 'docker build -t mypythonimage .'
            }
        }
        stage('Run'){
            steps{
                echo 'Running Docker Application'
                bat 'docker rm -f mycontainer || exit 0'
                bat 'docker run -d -p 5000:5000 --name mycontainer mypythonimage'
            }
        }
    }
    post{
        success{
            echo "successfully build docker application"
        }
        failure{
            echo "failed to build docker application"
        }
    }
}
