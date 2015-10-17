#Download the latest minimega repo from:
#http://minimega.org or https://github.com/sandia-minimega/minimega

**This fork has been modified for LivLab projects.**

**It's a fork of minimega 2.0**
- Added password protection for VNC sessions

You can change the password like this:
```
vm qmp vm_name '{ "execute": "change", "arguments": { "device": "vnc", "target": "password", "arg": "p4ssw0rd" } }'
```
```
Python code example:
        vmname = "kali"
        password = "hackthings"
        testcmd = """'{ "execute": "change", "arguments": { "device": "vnc", "target": "password", "arg": "%s" } }'"""%password
        os.system(minimega_cmd+"vm qmp "+vmname+" "+json.dumps(testcmd))
```
- Fixed bug in web.go. The map wasn't rendering Long correctly.
```
Changed
p.Long, err = strconv.ParseFloat(vm.Tags["lat"], 64)
to
p.Long, err = strconv.ParseFloat(vm.Tags["long"], 64)
```

**Thanks to the contributors at Sandia National Labs for making minimega.**