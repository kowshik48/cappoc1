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
				sh 'sudo rm -f *;sudo git clone https://github.com/kowshik48/cappoc1.git'
			}
		}
		stage('tfsvars create'){
			steps{
				sh 'sudo cp /home/ec2-user/vars.tf ./jenkins/'
			}
		}
		stage('terraform init'){
			steps{
				sh 'sudo /home/ec2-user/terraform init ./jenkins'
			}
		}
		stage('terraform plan'){
			steps{
			sh 'ls ./jenkins; sudo /home/ec2-user/terraform plan ./jenkins'
			}
		}
		stage('terraform apply'){
			steps{
			sh 'ls ./jenkins; sudo /home/ec2-user/terraform apply -no-color -auto-approve ./jenkins'
			}
		}
		stage('terraform ended'){
			steps{
				sh 'echo "Ended....!" '
			}
		}
		
	}
}
		

			