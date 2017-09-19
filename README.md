# ansible-apt-mirror
Ansible role to create an apt mirror

The purpose of this role is to take part of others ansible roles by calling him from git module (ansible)

## Prequisits
You need some space !
Please use a separate disk like /dev/sdb with LVM.
The config I use is:
```bash
pvcreate /dev/sdb
vgcreate APTVG /dev/sdb
lvcreate -n aptlv -l +100%FREE APTVG
mkfs -t ext4 /dev/mapper/APTVG-aptlv
```

Don't forget /etc/fstab
```bash
/dev/mapper/APTVG-aptlv /opt/apt-mirror ext4    defaults    1 2
```

## defaults vars

**apt_mirror_base_path:**

If you don't want sources in /opt/apt-mirror you can modify the main.yml file in defaults folder.

**apt_mirror_cron:**

Put True if you want cron.

**apt_mirror_cron_day:**

Please provide the day

**apt_mirror_cron_hour:**

Please provide the hour.





*Original credit from AutomationWithAnsible*
