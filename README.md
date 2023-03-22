# grafana-influx-docker-debian
Documenting the steps I took to set up grafana.  I used this webpage as reference https://stangneth.com/2021/07/15/grafana-influxdb-telegraf-mit-docker-compose/#:~:text=It%20is%20based%20on%20InfluxDB%202.0%2C%20Telegraf%20%26,the%20InfluxDB%20folder%20and%20create%20the%20docker-compose.yml%20file.


## Part 1 - Set up SSH key and clone this repository
Create / import your private key:
```
nano ~/.ssh/id_rsa
```
Create /import your public key:
```
nano ~/.ssh/id_rsa.pub
```
Test your keys with git:
```
ssh -T git@github.com
```
Clone this repository:
```
git clone git@github.com:vichanzo/ansible-apt.git
```
Edit the README with "nano README.MD" then push it to git.
```
git status
git add *
git commit -m "Updated README"
git push origin main
```


## Part 2 - Install Docker (assumes you are using Debian/Proxmox)

Add Docker Community Edition repo to APTx
```
sudo apt update -y
sudo apt install software-properties-common
curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
sudo apt update -y
```

Install Docker-CE
```
sudo apt install docker-ce docker-ce-cli -y
```

Verify Docker is installed
```
docker version
```

Enable and start Docker service
```
sudo systemctl enable docker
sudo systemctl start docker
```
