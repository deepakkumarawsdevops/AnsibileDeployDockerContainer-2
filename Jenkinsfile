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
stage(' Release docker image')
{

steps

{
echo 'Releasing'

sh 'ansible-playbook dockerimagepush.yml'

}
}

stage('Deployment')
{

steps
{

echo 'deploying'

sh 'ansible-playbook deployment.yml'

}
}


 }
}
