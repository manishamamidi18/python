```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/manishamamidi18/python-cicd.git'
            }
        }

        stage('Compile') {
            steps {
                bat 'python -m py_compile app.py test_app.py'
            }
        }

        stage('Test') {
            steps {
                bat 'python -m unittest test_app -v'
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Package') {
            steps {
                bat 'tar -a -c -f python-cicd.zip app.py test_app.py requirements.txt'
            }
        }
    }
}
```