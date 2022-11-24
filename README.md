# half-life-2

## What is this?

An improved version of the half-life theme for oh-my-posh, pushed to this repo so I don't lose it.

## Enabling last command

`.Env.POSH_LAST_COMMAND` is responsible for changing the console title to the last entered command and is updated by posh context.

### Powershell

Add this code block to your `$PROFILE`:

```ps1
function Set-EnvVar {
    $env:POSH_LAST_COMMAND=$((Get-History | Select-Object -Last 1).CommandLine)
}
New-Alias -Name 'Set-PoshContext' -Value 'Set-EnvVar' -Scope Global -Force
```
