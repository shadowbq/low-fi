## Install 

This is not a gem or even a nice app.. its an 8-track 

### Install Deps

```shell
$> mkdir -p /tmp/foo && cd /tmp/foo
$> wget wget https://raw.githubusercontent.com/shadowbq/low-fi/master/group/Gemfile
$> bundle install
Fetching gem metadata from https://rubygems.org/..
Fetching version metadata from https://rubygems.org/.
Resolving dependencies...
Using inifile 3.0.0
Using bundler 1.9.8
Bundle complete! 1 Gemfile dependency, 2 gems now installed.
Use `bundle show [gemname]` to see where a bundled gem is installe
```
### Drop in the Bins
```shell
$> mkdir -p /opt/bin && cd /opt/bin
$> wget https://raw.githubusercontent.com/shadowbq/low-fi/master/group/group_do
$> wget https://raw.githubusercontent.com/shadowbq/low-fi/master/group/group_put
```

### Edit the INI file

Edit the `.group.ini` file to include the server and sensor sets.

```shell
$> cd ~/.
$> wget wget https://raw.githubusercontent.com/shadowbq/low-fi/master/group/.group.ini
$> vi ~/.group.ini
```

## Extended Help

```shell
$>  /opt/bin/group_do --help
GROUP_DO (Version 1.0.1 )
 Usage: ./group_do [options] "[shell commands]"
 Note: [shell commands] must be escaped.

  Server List:
    -a, --all                        All Servers (default if none selected)
    -s, --sensors                    Sensors

  Login Options (Select One):
    -i, --interactive                Connect via subshell with current user
    -x, --root                       Connect via root rather than current user
    -z, --sudo                       Connect via current user and sudo

  Common Options:
        --skip-config-file           skip .ssh configuration file
    -v, --verbose                    Verbose Debugging Enabled
    -h, --help                       Display this screen
```

## Example Run

```shell
$>  /opt/bin/group_do -s 'id'
uid=1002(macgregors) gid=1002(macgregors) groups=1002(macgregors),0(wheel)
uid=1001(macgregors) gid=1001(macgregors) groups=1001(macgregors),0(wheel)
uid=1002(macgregors) gid=1002(macgregors) groups=1002(macgregors),0(wheel)
uid=1001(macgregors) gid=1001(macgregors) groups=1001(macgregors),0(wheel)
```

## Example Run with `sudo` 

```shell
$>  /opt/bin/group_do -s -z 'id'
uid=0(root) gid=0(wheel) groups=0(wheel),5(operator)
uid=0(root) gid=0(wheel) groups=0(wheel),5(operator)
uid=0(root) gid=0(wheel) groups=0(wheel),5(operator)
uid=0(root) gid=0(wheel) groups=0(wheel),5(operator)
```
