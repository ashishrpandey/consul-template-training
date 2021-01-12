## Prerequisite:

- Consul is running and accessible 
- The consul-template is already installed 
- input-template.tpl file is present with some variable 

        git clone https://github.com/ashishrpandey/consul-template-training
        cd consul-template-training

## Check the content of input-template.tpl
  
    cat input-template.tpl
    This is my sample value of key - {{ key "foo" }}

    
## Apply consul template. Execute the below command

    consul-template -template "input-template.tpl:output.txt"

This will hold the screen.

## Put some value in Consul KV

Create a duplicate terminal and put some value of the variable mentioned in inouttemplate.tpl 

    consul kv put foo bar
    
## Check the output file 
Open the output.txt

    cat output.txt 
      This is my sample value of key - bar


