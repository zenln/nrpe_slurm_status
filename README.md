# nrpe_slurm_status
Bash slurm status check

## Usage
In nagios config file[Default location with nrpe /etc/nrpe.cfg] define costum command:
```bash
command[check_slurm]=/user/downloaded/path/check_slurm_status
```

## User Permission and Selinux permission
You may have to consider user permission for user running this script with nrpe user.
<br />
Also for selinux please add appropriate selinux type for the sctipt.
- An easy configure selinux would be 
```bash
# ausearch -m avc -ts recent | grep nagios |audit2allow -m check_slum
# ./check_slurm.pp 
```

Allow sinfo socket to connect to nrpe deamon. 
```bash
setsebool -P nis_enabled 1
```

