pipeline{
	agent any
	stages{
		stage('Git Checkout'){
			steps{
				echo "Compiled successfully";
				git credentialsId: '355b7123-55c3-4790-b14a-c350d2db39f6', url: 'https://github.com/vigneshpandi2907/first-pipeline-script-jenkins.git'
			}
		}
		stage('Build'){
			steps{
				echo "Building the checkout project!";
				bat 'Build.bat'
			}
		}
		stage('Unit-Test'){
    		steps{
    			echo "Building the checkout project!";
    			bat 'Unit.bat'
    		}
		}
		stage('Quality-Gate'){
			steps{
				echo "SonarQube Quality gate passed successfully";
				bat 'Quality.bat'

			}
		}
		stage('Deploy'){
			steps{
				echo "Pass!";
				bat 'Deploy.bat'

			}
		}
	}
	post{
		always{
			echo 'This will always run'
		}
		success{
			echo 'This will only if successful'
		}
		failure{
			echo 'This will run only if failed'
		}
		unstable{
			echo 'This will run only if the run was marked as unstable'
		}
		changed{
			echo 'This will always run only if thee state if the pipline has changed'
		
		}
	}
}
	
