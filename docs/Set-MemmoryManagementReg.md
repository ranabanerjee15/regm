---
external help file: regm-help.xml
Module Name: regm
online version:
schema: 2.0.0
---

# Set-MemmoryManagementReg

## SYNOPSIS
Sets Registry for memory management on one or many servers

## SYNTAX

```
Set-MemmoryManagementReg [[-ComputerName] <String[]>] [-ShowProgress] [<CommonParameters>]
```

## DESCRIPTION
This function sets the registry for memmory management.
- Settings modified are under the the following path 'HKLM:\System\CurrentControlSet\Control\Session Manager\Memory Management'
- Following Dword item property is added with a keyword 'FeatureSettingsOverride' and value 72
- Following Dword item property is added with a keyword 'FeatureSettingsOverrideMask' and value 3

## EXAMPLES

### EXAMPLE 1
```powershell
Set-MemmoryManagementReg
```

### EXAMPLE 2
```powershell
Set-MemmoryManagementReg -ComputerName Server1,Server2,Server3
```

### EXAMPLE 3
```powershell
Set-MemmoryManagementReg -ComputerName Server1,Server2,Server3 -ShowProgress
```

### EXAMPLE 4
```powershell
Set-MemmoryManagementReg -ComputerName (get-content c:\ServerList.txt) -ShowProgress
```

### EXAMPLE 5
```powershell
Set-MemmoryManagementReg -ComputerName (get-content c:\ServerList.txt) -ShowProgress | Export-csv c:\Results.csv
```

### EXAMPLE 6
```powershell
Set-MemmoryManagementReg -ComputerName (Import-Csv c:\ServerList.csv | Select -ExpandProperty Servers) -ShowProgress | Export-csv c:\Results.csv
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
This function modifies registry.
for execution on other servers it needs remoting to be enabled.

## RELATED LINKS
