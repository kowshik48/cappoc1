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
				sh 'sudo cp /home/jenkins/backup/vars.tf  /var/lib/jenkins/workspace/Infra_Terraform_Pipeline/cappoc1'
				sh 'cd /var/lib/jenkins/workspace/Infra_Terraform_Pipeline/cappoc1'
			}
		}
		stage('terraform init'){
			steps{
				sh 'cd /var/lib/jenkins/workspace/Infra_Terraform_Pipeline/cappoc1; sudo terraform init /var/lib/jenkins/workspace/Infra_Terraform_Pipeline/cappoc1'
			}
		}
		stage('terraform plan'){
			steps{
			sh 'sudo terraform init /var/lib/jenkins/workspace/Infra_Terraform_Pipeline/cappoc1'
			sh 'sudo terraform plan /var/lib/jenkins/workspace/Infra_Terraform_Pipeline/cappoc1'
			}
		}
		stage('terraform apply'){
			steps{
			sh 'sudo terraform apply -no-color -auto-approve /var/lib/jenkins/workspace/Infra_Terraform_Pipeline/cappoc1'
			}
		}
		stage('terraform ended'){
			steps{
				sh 'echo "Ended....!" '
			}
		}
		
	}
}
		

			
