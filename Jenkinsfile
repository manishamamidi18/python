```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/manishamamidi18/python.git'
            }
        }

        stage('Compile') {
            steps {
                bat 'python -m py_compile app.py apptest.py'
            }
        }

        stage('Test') {
            steps {
                bat 'python -m unittest apptest -v'
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Package') {
            steps {
                bat 'tar -a -c -f python-cicd.zip app.py apptest.py requirements.txt'
            }
        }
    }
}
```