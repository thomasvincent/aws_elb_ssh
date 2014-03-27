# Ruby AWS Tools

get_elb_nodes.rb will return all nodes in an ELB group with there private IP Addresses.  This makes it easier to create an SSH or Cluster SSH config for nodes that might be part of an Autoscale group and are dynamic


## Requirements:
gem install aws-sdk

gem install trollop

Copy config/config.rb.sample to config/config.rb and add your AWS Key info

##Usage:

ruby get_elb_nodes.rb -n ELB_GROUP_NAME

##SSH Config Output
This will output to STDOUT SSH config blocks for each instance found in the ELB group

ruby get_elb_nodes.rb -n ELB_GROUP_NAME -s -u ubuntu -k ~/.ssh/mykey.pem

