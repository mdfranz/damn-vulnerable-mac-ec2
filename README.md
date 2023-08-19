# damn-vulnerable-mac-ec2

```
    ┌───┬──┐   __|  __|_  )
    │ ╷╭╯╷ │   _|  (     /
    │  └╮  │  ___|\___|___|
    │ ╰─┼╯ │  Amazon EC2
    └───┴──┘  macOS Ventura 13.5
```


## The Idea

Create isolated VPC with
- VPC Flow Logs
- Route 53 Resolver Logs

Create the Instances


### Disable Secure SSH configuration

Edit `/usr/local/aws/ec2-macos-init/init.toml`

```
# Apply secure settings to SSHD on every boot
# To manage ssh_config separately, disable this module
[[Module]]
    Name = "EC2SuggestedDefaultConfigSecurity"
    PriorityGroup = 3 # Third group
    RunPerBoot = true # Run every boot to enforce these parameters
    FatalOnError = true # Security settings, must succeed
    [Module.SystemConfig]
        secureSSHDConfig = true
```



## AWS Docs


