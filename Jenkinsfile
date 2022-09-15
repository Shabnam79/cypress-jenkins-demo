
pipeline {
	agent any
	stages {
		stage('Clone Git Repo'){
				steps{
					git 'https://github.com/qaboxletstest/cypress-jenkins-demo.git'
		    }
		}
		stage('Install Dependencies'){
				steps{
					sh 'npm install'
				}
		}
		stage('Run Tests'){
				steps{
					sh 'npm test'
				}
		}
		stage('Publish HTML Report'){
				steps{
					publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'cypress/reports/mochareports', reportFiles: 'report.html', reportName: 'HTML Report', reportTitles: ''])
				}
		}
	}
}

