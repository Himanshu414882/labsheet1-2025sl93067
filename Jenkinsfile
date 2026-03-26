pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage (listing files)'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Running calculator tests...'

                // Example Python test execution
                sh '''
                echo "Testing calculator functions"

                python3 - <<EOF
def add(a, b): return a + b
def sub(a, b): return a - b
def mul(a, b): return a * b
def div(a, b): return a / b

print(add(2,3))
print(sub(5,2))
print(mul(3,4))
print(div(10,2))
EOF
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment stage (simulated)'
                echo 'Application deployed successfully!'
            }
        }
    }
}