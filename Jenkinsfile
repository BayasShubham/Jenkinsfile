
You said:
pipeline {
    agent any
    
    environment {
        GIT_REPO = 'git@github.com:BayasShubham/test12.git'
        BRANCH = 'main'  // Adjust to your branch name
    }
    
    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning the repository...'
                // Clone the repository
                git branch: "${BRANCH}", url: "${GIT_REPO}"
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Build command, e.g., Gradle or Maven
                // Uncomment the one that applies to your project and comment the other
                // sh './gradlew build'      // For Gradle
                // sh 'mvn clean install'    // For Maven
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running the application...'
                // Run the application (adjust to your application start command)
                sh 'java -jar build/libs/your-application.jar' // For Gradle jar output
                // sh 'java -jar target/your-application.jar'   // For Maven jar output
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
