# Ruby AWS Tools

get_elb_nodes.rb will return all nodes in an ELB group with there private IP Addresses.  This makes it easier to create an SSH or Cluster SSH config for nodes that might be part of an Autoscale group and are dynamic


## Requirements:
1. gem install aws-sdk
2. gem install trollop
3. Copy config/config.rb.sample to config/config.rb and add your AWS Key info

##Usage:

###Basic:
ruby get_elb_nodes.rb -n ELB_GROUP_NAME

###Advanced:
ruby get_elb_nodes.rb -n ELB_GROUP_NAME -s -u ubuntu -k ~/.ssh/mykey.pem -p web

##SSH Config Output
This will output to STDOUT SSH config blocks for each instance found in the ELB group

ruby get_elb_nodes.rb -n ELB_GROUP_NAME -s -u ubuntu -k ~/.ssh/mykey.pem

Another cool feature is prefixing.

Lets say you have 5 web servers in an ELB group
By specifing a prefix (-p web ) of web the following Hostnames will be generated:
ruby get_elb_nodes.rb -n ELB_GROUP_NAME -s -u ubuntu -k ~/.ssh/mykey.pem -p web

Hostname web1

Host 1.1.1.1

Hostname web2

Host 1.1.1.2

etc....
