# POWERSHELL

## Search in Files
`dir -rec *.js | sls "products"`

## Add Path
`Set-ItemProperty -Path ‘Registry::HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Session Manager\Environment’ -Name PATH –Value $newPath`

## All ENV variables start with $
### differs from powershell-specific variables
`$env:path`

## Browse registry like file-system
`cd HKLM:`
