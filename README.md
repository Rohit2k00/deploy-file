Jenkins installation

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install Jenkins
sudo apt install fontconfig openjdk-17-jre


agents package

sudo apt update -y

# Install Python and pip
sudo apt install -y python3 python3-pip

# Install AWS CodeDeploy agent
sudo apt install -y ruby wget
wget https://aws-codedeploy-ap-northeast-1.s3.amazonaws.com/latest/installchmod +x ./install
sudo ./install auto
sudo service codedeploy-agent start
