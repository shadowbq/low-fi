## Install 

```shell
cd /opt/bin/
wget https://raw.githubusercontent.com/shadowbq/low-fi/master/group/group_do
wget https://raw.githubusercontent.com/shadowbq/low-fi/master/group/group_put

cd ~/.
wget wget https://raw.githubusercontent.com/shadowbq/low-fi/master/group/.group.ini
```
## Edit the INI file.

Edit the `.group.ini` file to include the server and sensor sets.

## Extended Help

```shell
$ ./group_do --help
GROUP_DO (Version 1.0 )
 Usage: ./group_do [options] 
 Note: Commands must be escaped.

 Server List:
    -a, --all                        All Servers
    -s, --sensors                    Sensors

  Global Options:
    -x, --root                       Connect via root rather than current user
    -z, --sudo                       Connect via current user and sudo
    -v, --verbose                    Verbose Debugging Enabled
    -h, --help                       Display this screen
```

## Example Run

```shell
./group_do -s 'id'
uid=1002(macgregors) gid=1002(macgregors) groups=1002(macgregors),0(wheel)
uid=1001(macgregors) gid=1001(macgregors) groups=1001(macgregors),0(wheel)
uid=1002(macgregors) gid=1002(macgregors) groups=1002(macgregors),0(wheel)
uid=1001(macgregors) gid=1001(macgregors) groups=1001(macgregors),0(wheel)
```

## Example Run with `sudo` 

```shell
./group_do -s -z 'id'
uid=0(root) gid=0(wheel) groups=0(wheel),5(operator)
uid=0(root) gid=0(wheel) groups=0(wheel),5(operator)
uid=0(root) gid=0(wheel) groups=0(wheel),5(operator)
uid=0(root) gid=0(wheel) groups=0(wheel),5(operator)
```
