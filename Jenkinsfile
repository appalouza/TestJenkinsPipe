pipeline {
	agent any
	stages {
		stage("Cleaning Stage") {
			steps {
				bat "mvn clean"
			}
		}
		stage("Testing Stage") {
			steps {
				bat "mvn test"
			}
		}
		stage("Packaging Stage") {
			steps {
				bat "mvn package"
			}
		}
		stage("COnsolidate Results") {
			steps {
				input("Do You Want to capture results?")
				junit '**/target/surefile-reports/TEST-*xml'
				archive 'target/*.jar"
			}
		}
	}
}
