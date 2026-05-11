check list:
- list user có quyền sudo, nếu có thì xử lý như user root
- add ssh key
- backup lại public key trong file `.ssh/authorized_keys`
- xóa public key cũ
- đổi password

ssh key truongblx và phuctv
```
#ionah
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIBV2zHGcYRcaXk7iokU3n5y2qtIiFu2UFl3SreOtvkep truongblx@dso
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCx5rVqUQIrB+6I5JmIM6o/gALt1WeCnomEDQkbq3+x7gk9RdBAp2XdiQbSmTQ2pOP0bEdtqll5KNL7G1E49DcIYVotWvHBAR2cxS1G1VDTH6bNgkNPT66M2oYlBlCNkxzUmKEf2kCwsUBcBOvjrxdIabsR22m8ESgby/irJXIXDNLOfsizvYZtnM56ljZlwn8rmAELenSe/o1hwsOv+B8vqs2kiV00KhEMG18qpSjh0tNdejOqmPwgyyuulDs6ucYSnDL7XDV1TCtR/JCYs2/YHMDJXt4KwpAZrtNmveOo1koyjTR8xiUKP9WtDOXEFAZDFoC/n+mlabIa9wytMwaOXfYVOCGgr9tbB2bxyzFJQZpGLU4Wkxi2qZk6kbvkyowl24xIW5J6RrtPIcF79Loe8GeAMHhtiuMRdrwV0VUgPNxBlL/CEj2r0wz3XUUmpIaJ6pl4ABTTJJwkrK4CEtMXEjiH5rrGqQfYk57OS1jkoZPqukr0eOkiU6KW41DD+9M= phuc.tran

```

```sh
cd .ssh
cp -a authorized_keys authorized_keys.bak
echo > authorized_keys
vim authorized_keys
```

`ssh root@10.250.104.30`
`ssh root@10.250.104.51`
`ssh root@10.250.104.53`
`ssh root@10.250.104.11`
`ssh root@10.250.104.12`
`ssh root@10.250.104.13`
`ssh root@10.250.104.21`
`ssh root@10.250.104.22`
`ssh root@10.250.104.23`
`ssh root@10.250.104.31`
`ssh root@10.250.104.32`
`ssh root@10.250.218.11`

```
passwd root
passwd user
```