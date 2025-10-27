pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'Code pulled from GitHub successfully!'
            }
        }

        stage('Build HTML') {
            steps {
                script {
                    echo "Listing files in workspace..."
                    bat 'dir' // (Use sh 'ls' if Linux)
                }
            }
        }

        stage('Display Link') {
            steps {
                script {
                    // Construct local file path (Jenkins workspace HTML file)
                    def htmlFile = "${env.WORKSPACE}\\bmi-calculator.html"
                    def link = "file:///${htmlFile.replace('\\', '/')}"
                    echo "✅ Your HTML file has been generated."
                    echo "👉 Open the page here: ${link}"
                    echo "<a href='${link}' target='_blank'>Click to open BMI Calculator</a>"
                }
            }
        }
    }
}
