# Docker Course

- Download and install Docker
- Signin /up
- Add code completion to docker zsh: 
Paste 
etc=/Applications/Docker.app/Contents/Resources/etc
ln -s $etc/docker.zsh-completion /usr/local/share/zsh/site-functions/_docker
ln -s $etc/docker-compose.zsh-completion /usr/local/share/zsh/site-functions/_docker-compose

In zsh command line. 

# Kill and restart command line. If it doesn’t work, 
Run 
- rm -v ~/.zcompdump*
- Kill and restart command line. 
