pipeline{
	agent{
		node{
			label 'master'
		}
	}
	stages{
		stage('terraform started'){
			steps{
				sh 'echo "Started...!" '
			}
		}
		stage('git clone'){
			steps{
				sh 'sudo rm -rf *;sudo git clone https://github.com/kowshik48/cappoc1.git'
			}
		}
		stage('tfsvars create'){
			steps{
				sh 'sudo cp /home/jenkins/backup/vars.tf  /var/lib/jenkins/workspace/terraformpipeline/cappoc1'
				sh 'cd /var/lib/jenkins/workspace/terraformpipeline/cappoc1'
			}
		}
		stage('terraform init'){
			steps{
				sh 'terraform init'
			}
		}
		stage('terraform plan'){
			steps{
			sh 'ls /var/lib/jenkins/; sudo terraform plan /var/lib/jenkins/'
			}
		}
		stage('terraform apply'){
			steps{
			sh 'ls /var/lib/jenkins/;  terraform apply -no-color -auto-approve /var/lib/jenkins/'
			}
		}
		stage('terraform ended'){
			steps{
				sh 'echo "Ended....!" '
			}
		}
		
	}
}
		

			
