# grafana-influx-docker-debian


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
git commit -m "Updated README"
git push origin main
```
