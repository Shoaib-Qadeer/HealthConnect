pipeline {
   agent any

   tools {
   maven 'Maven 3.8.6'
   jdk 'Java 16'
   }


//   environment {
  // JAVA_HOME = "${tool name: 'Java 16', type: 'jdk'}"
  // PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
 //  }


    options {
        buildDiscarder logRotator(
                    daysToKeepStr: '16',
                    numToKeepStr: '10'
            )
    }
    stages {
        stage('Cleanup Workspace') {
        environment {
                 JAVA_HOME = "${tool 'Java 16'}"
                 PATH = "${env.JAVA_HOME}/bin:${env.PATH}"
             }
            steps {
                cleanWs()
                sh """
                echo Java home is $JAVA_HOME
                echo Java home is $JAVA_HOME
                echo PATH is $PATH
                echo Java path \$(which java)
                echo Java version is \$(java --version)
                echo Maven version is \$(mvn --version)
                echo "Cleaned Up Workspace For Project"
                """
            }
        }

//         stage('Code Checkout') {
//             steps {
//                 checkout([
//                     $class: 'GitSCM',
//                     branches: [[name: '*/main']],
//                     userRemoteConfigs: [[url: 'https://gitlab.com/billyjeans/HealthConnect']]
//                 ])
//             }
//         }
//
//         stage(' Unit Testing') {
//            steps {
//                 echo "Running Unit Tests"
//
//                         // Set up the environment
//                         sh 'mvn clean install'
//
//                         // Run JUnit tests
//                         sh 'mvn test'
//             }
//         }
//
//         stage('Code Analysis') {
//             steps {
//                 sh """
//                 echo "Running Code Analysis"
//                 """
//             }
//         }
//
//         stage('Build Deploy Code') {
//             when {
//                 branch 'main'
//             }
//             steps {
//                 sh """
//                 echo "Building Artifact"
//                 """
//
//                 sh """
//                 echo "Deploying Code"
//                 """
//             }
//         }

    }
}
