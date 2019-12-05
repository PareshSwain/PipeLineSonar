pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning the code..'
	git 'https://github.com/PareshSwain/SonarTest.git'
            }
        }
        stage('Clean') {
            steps {
                echo 'Clean..'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true clean"
        	}

            }
        }
        stage('Compile') {
            steps {
                echo 'Compiling....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true compile"
        	}
		}
		}

	stage('Test') {
            steps {
                echo 'Testing....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true test"
        	}
		}
		}

	stage('Package') {
            steps {
                echo 'Packaging....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true package"
        	}
		}
		}

stage('Deploy') {
            steps {
                echo 'deploying....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true deploy"
        	}
		}
		}
		
		stage('sonar') {
            steps {
                echo 'sonar....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true sonar:sonar"
        	}
		}
		}

stage('checkstyle') {
            steps {
                echo 'checkstyle....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true checkstyle:checkstyle"
        	}
		}
		}

stage('pmd') {
            steps {
                echo 'pmd....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true pmd:pmd"
        	}
		}
		}

stage('findbugs') {
            steps {
                echo 'findbugs....'
		withMaven(jdk: 'JDK1.8', maven: 'MAVEN') {
    		// some block
        	bat "mvn -Dmaven.test.failure.ignore=true findbugs:findbugs"
        	}
		}
		}
         
  
    }
}
