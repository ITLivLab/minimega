#Download latest minimega repo from minimega.org or https://github.com/sandia-minimega/minimega
This fork has been modified for LivLab projects.
1. Added password protection for VNC sessions
You can change the password like this:
vm qmp vm_name '{ "execute": "change", "arguments": { "device": "vnc", "target": "password", "arg": "p4ssw0rd" } }'

Python code example:
        vmname = "kali"
        password = "hackthings"
        testcmd = """'{ "execute": "change", "arguments": { "device": "vnc", "target": "password", "arg": "%s" } }'"""%password
        os.system(minimega_cmd+"vm qmp "+vmname+" "+json.dumps(testcmd))

2. Fixed bug in web map rendering. It wasn't mapping long tag correctly

Thanks to contributors at Sandia National Labs for making minimega.