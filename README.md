# ansible-junos-l3vpn

This repo has a project to demonstrate configuring L3VPN on JUNOS routers using Ansible. 

The attached PPT file 'APRICOT_2017-Automating_L3VPNs_with_Ansible-Nitin_Vig_v1.1.pptx' has details on the topology.

Steps:
1) Gather facts:
To get facts from the JUNOS routers, run the 'pb.test.get_facts.yaml' playbook. Un-hash the examples in the file to test them.

2) Initial a temporary directory to store configs:
run the 'pb.init.cleanup.yaml' playbook

3) Push base config:
Run the 'pb.conf.base_config.yaml' playbook

4) Generate variables:
Run the following playbooks to generate variables that will be used to create VPNs and to run some tests against them:
(run the playbooks in the below order):
 - pb.generate.vpn.yaml
 - pb.generate.jsnapy.yaml
 
5) Configure the VPN service:
Run the 'pb.conf.vpn_service.yaml' playbook to configure the VPNs.

6) Run tests to check the service:
Run the 'pb.test.vpn_service.yaml' playbook to test the VPN service.
