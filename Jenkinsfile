pipeline

{
agent {label 'ansiblebuild'}
stages


{

stage('Build the project')
{
  steps

{
 sh 'echo "Building "'
 sh 'mvn package'
 sh 'mvn install'
 sh 'echo "job executed successfully"'

}

 }
stage ('Build Docker image using Ansible using war file')

{
steps

{
 echo 'Building using docker'
 sh 'ansible-playbook dockerimage.yml'
}

}
 }
}
