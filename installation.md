## Download the tar file

    wget https://releases.hashicorp.com/consul-template/0.25.1/consul-template_0.25.1_linux_amd64.tgz


## Extract and move it 

      tar -zxvf consul-template_0.25.1_linux_amd64.tgz
      mv consul-template /usr/bin/

## Verify 

    consul-template --help 
