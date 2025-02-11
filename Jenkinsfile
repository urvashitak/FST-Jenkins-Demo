pipeline {
    agent any

 environment {
        JAVA_HOME = 'C:\Program Files\Java\jdk-17.0.1'
    }


    stages {
        stage("Build") {
            steps {
                sh "mvn compile"
            }
        }

        stage("Test") {
            steps {
                wrap([$class: "Xvfb", debug: true, displayName: 7,displayNameOffset: 0, timeout:10]) {
                    sh "mvn test"
                }
            }
        }
        stage("Report") {
            steps {
                step([$class: 'Publisher'])"
            }
        }


        stage("Post_Actions") {
            steps {
                echo 'Tests finished'
            }
        }
    }
}
