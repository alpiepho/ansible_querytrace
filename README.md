
# Remote Query Trace using tcpdump

This is a script and ansible playbook that implements most of the Query Trace features backend.

## The bash script

The bash script sets up paramters for Ansible, then gathers all the result files and merges
them into a single csv file, similar to how Manager does this.

## The Ansible playbook

Hoepfully the playbook (querytrace.yml) is clear as to what is going on.  

It might be faster if there remote file get/remove were combined, to reduce the number of tasks.

It might be cleaner to generate pcap files instead of text files, then do all processing post remote-run.

## The inventory Files

For testing, all the inventory servers are pointing to the same server.  This is a test-only
configuration.  Ideally, this file 

## Limitations

Although, the number of forks can be set in the local ansible.cfg file, the pyhsical limit of the server system is really the limiting factor.  From observation, if the number of forks is less than the number of servers in the inventory file, then the remote tcpdump calls are batched up to the number of forks.

Using Ansible requires password-less ssh access.  I'm not sure how this would be done with
an ssh user/password.

## Installing Ansible on Centos6

The most obvious way to run this Ansible playbook is to run it from the Manager itself.

TODO: try the install process

## Installing Ansible on x86

An alternative way to run this Ansible playbook is to run it from an x86 system not included in the query.

TODO: try the install process


## Other Installations

We will leave other installations up to the user.  Using Google search should result in several tutorials.  

For the record, the Ansible playbook was developed from a Mac.

## Next Steps

There are really no next steps.  This project can serve as an example of using Ansible, or possibly could be expanded for working with customers.

There is a tutorial that I thought might be interesting, but have not had the time to follow up on:
https://medium.com/@brad.simonin/learning-ansible-with-centos-7-linux-12461043fd02
