// Declarative Pipeline
pipeline {
    // Set up the docker agent the jenkins slave will run on
    //  agent { docker { image 'python:3.8' } }
    agent { dockerfile true  }

    // Write out what happens each stage
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'python --version'
                // sh 'sudo pip install -r Game/requirements.txt'
                sh 'python3 Game/py_compileCheck.py'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                // Pytest here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'python3 Game/game.py'
            }
        }
    }
}

// Scripted Pipeline
// node{
//     Stage 'Checkout'
//         echo 'Checkout Stage'
//         checkout scm

//     Stage 'Build'
//         echo 'Building Stage'
//         sh 'python --version'
//         sh 'python3 Game/py_compileCheck.py'

//     Stage 'Test'
//         echo 'Test Stage'
//         //Pytest here

//     Stage 'Deploy'
//         echo 'Test Stage'

// }