From docker.io/istio/pilot:1.1.0-rc.5


EXPOSE 40000

RUN sudo apt-get install -y software-properties-common 
RUN sudo add-apt-repository ppa:longsleep/golang-backports -y
RUN sudo apt-get update -y
RUN sudo apt-get install golang-go -y

ADD files/dlv /root/go/bin/dlv
RUN sudo cp /root/go/bin/dlv /usr/local/bin/dlv
RUN chmod +x /usr/local/bin/dlv
ENTRYPOINT ["/usr/local/bin/dlv", "--listen=:40000", "--headless=true", "--api-version=2", "exec", "/usr/local/bin/pilot-discovery", "--"]
