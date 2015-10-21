# docker-keybox
KeyBox is an open-source web-based SSH console that centrally manages administrative access to systems.
Web-based administration is combined with management and distribution of user's public SSH keys.
Key management and administration is based on profiles assigned to defined users.

## KeyBox - Version: 2.84.00

## How to use this image
```
	$ docker run -d -v /my/own/datadir:/a/keydb -p 8443:8443 adito/keybox
```
now you can access keybox at "https://host-ip:8443"

## Variables

Example:
```
	$ docker run -d -v /my/own/datadir:/a/keydb -p 8443:8443 -e enableOTP=false adito/keybox
```
I disabled two-factor-authentication in this example

#### here you can find all variables and their default values

set to true to regenerate and import SSH keys
```
resetApplicationSSHKey=false
```

SSH Key Type 'dsa' or 'rsa' for generated keys
```
sshKeyType=rsa
```

SSH Key Length for generated keys
```
sshKeyLength=2048
```

private ssh key, leave blank to generate key pair
```
privateKey=
```

public ssh key, leave blank to generate key pair
```
publicKey=
```

default passphrase, leave blank for key without passphrase
```
defaultSSHPassphrase=${randomPassphrase}
```

enable audit
```
enableInternalAudit=false
```

keep audit logs for in days
```
deleteAuditLogAfter=90
```

set an audit log server using log4j (ex: logstash). Edit the log4j.xml to configure appender.
```
auditLogAppender=
```

The number of seconds that the client will wait before sending a null packet to the server to keep the connection alive
```
serverAliveInterval=60
```

default timeout in minutes for websocket connection (no timeout for <=0)
```
websocketTimeout=0
```

enable SSH agent forwarding
```
agentForwarding=false
```

enable two-factor authentication
```
enableOTP=true
```

enable key management
```
keyManagementEnabled=true
```

set to true to generate keys when added/managed by users and enforce strong passphrases set to false to allow users to set their own public key
```
forceUserKeyGeneration=true
```

authorized_keys refresh interval in minutes (no refresh for <=0)
```
authKeysRefreshInterval=120
```

Regular expression to enforce password policy
```
passwordComplexityRegEx=((?=.*\\d)(?=.*[A-Z])(?=.*[a-z])(?=.*[!@#$%^&*()+=]).{8\,20})
```

Password complexity error message
```
passwordComplexityMsg=Passwords must be 8 to 20 characters\, contain one digit\, one lowercase\, one uppercase\, and one special character
```

specify a external authentication module (ex: ldap-ol, ldap-ad).  Edit the jaas.conf to set connection details
```
jaasModule=
```


## Supported Docker versions

This image is officially supported on Docker version 1.8.3.

Support for older versions (down to 1.6) is provided on a best-effort basis.

