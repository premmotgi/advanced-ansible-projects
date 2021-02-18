1. When you want to execute same script on multiple servers stratergies are used
2. By default, ansible starts running scripts on all the servers paralelly
3. this execution is then managed by servers on its own and ansible only checks status to determine if its finished
4. but suppose there are 100 servers and we want execute only on 3 servers at a time?
- at this point, module "serial" is used. Serial takes value of number of servers to run script on.
- serial basically limits execution to specific number of servers
ege.
name:
serial: 3 # run on 3 servers at a time

5. Ansible basically uses fork process for each copy of script execution
6. By default ansible runs on 5 servers, even if you provide serial: 100, it will still execute for 5. since it is preconfigured in ansible.cfg. file
7. You can change value in the ansible.cfg file to achieve more parallelism.
value to change>>>>

forks=5 # change this value to any value you want to achieve paralellism for your script.
