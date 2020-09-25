---
external help file: regm-help.xml
Module Name: regm
online version:
schema: 2.0.0
---

# Get-MemmoryManagementReg

## SYNOPSIS
Gets the registry setting for Memmory Management.

## SYNTAX

```
Get-MemmoryManagementReg [[-ComputerName] <String[]>] [-ShowProgress] [<CommonParameters>]
```

## DESCRIPTION
This function gets the registry for memmory management.
- Settings retrived are under the the following path 'HKLM:\System\CurrentControlSet\Control\Session Manager\Memory Management'
- Following Dword item property with a keyword 'FeatureSettingsOverride' and 'FeatureSettingsOverrideMask' are queried

## EXAMPLES

### EXAMPLE 1
```powershell
Get-MemmoryManagementReg
```

### EXAMPLE 2
```powershell
Get-MemmoryManagementReg -ComputerName Server1,Server2,Server3
```

### EXAMPLE 3
```powershell
Get-MemmoryManagementReg -ComputerName Server1,Server2,Server3 -ShowProgress
```

### EXAMPLE 4
```powershell
Get-MemmoryManagementReg -ComputerName (get-content c:\ServerList.txt) -ShowProgress
```

### EXAMPLE 5
```powershell
Get-MemmoryManagementReg -ComputerName (get-content c:\ServerList.txt) -ShowProgress | Export-csv c:\Results.csv
```

### EXAMPLE 6
```powershell
Get-MemmoryManagementReg -ComputerName (Import-Csv c:\ServerList.csv | Select -ExpandProperty Servers) -ShowProgress | Export-csv c:\Results.csv
```

## PARAMETERS

### -ComputerName
Computer name can be one or many Servers.
by default if no ComputerName is mentioned, it will try and apply the settings to itself.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: $env:COMPUTERNAME
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShowProgress
If this switch is turned on, it will show progress of the execution.
This will be only applicable while processing multiple Servers.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
for execution on other servers it needs remoting to be enabled.

## RELATED LINKS
