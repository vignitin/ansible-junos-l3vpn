# ansible-junos-l3vpn

This repo has a project to demonstrate configuring L3VPN on JUNOS routers using Ansible. 

The attached PPT file 'APRICOT_2017-Automating_L3VPNs_with_Ansible-Nitin_Vig_v1.1.pptx' has details on the topology.

<b>Steps:</b><br>
<b>1) Gather facts:</b><br>
To get facts from the JUNOS routers, run the 'pb.test.get_facts.yaml' playbook. Un-hash the examples in the file to test them.

<b>2) Initial a temporary directory to store configs:</b><br>
run the 'pb.init.cleanup.yaml' playbook

<b>3) Push base config:</b><br>
Run the 'pb.conf.base_config.yaml' playbook

<b>4) Generate variables:</b><br>
Run the following playbooks to generate variables that will be used to create VPNs and to run some tests against them:
(run the playbooks in the below order):
 - pb.generate.vpn.yaml
 - pb.generate.jsnapy.yaml
 
<b>5) Configure the VPN service:</b><br>
Run the 'pb.conf.vpn_service.yaml' playbook to configure the VPNs.

<b>6) Run tests to check the service:</b><br>
Run the 'pb.test.vpn_service.yaml' playbook to test the VPN service.
