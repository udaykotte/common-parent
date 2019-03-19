pipeline {

    agent {

        label "windows"

    }

    tools {

        maven 'apigee-maven'

        java 'java1.8'

    }

    stages {

        stage ('Initialize') {

            steps {

                bat '''

                    echo "PATH = %PATH%"

                    echo "MAVEN_HOME = %MAVEN_HOME%"

                '''

            }

        }



        stage ('Build') {

            steps {

                    bat 'cd NumberGenerator & mvn install'

            }

             post {

                success {

                    junit 'NumberGenerator/target/surefire-reports/*.xml'

                        }

                 }

               



           

            }

        }

    

}
