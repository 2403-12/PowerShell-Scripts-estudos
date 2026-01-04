Script PowerShell para verificação de programas instalados no seu computador

$paths = @(
    "HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\*",
    "HKLM:\Software\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\*",
    "HKCU:\Software\Microsoft\Windows\CurrentVersion\Uninstall\*"
)

Get-ItemProperty $paths |
Select-Object DisplayName, DisplayVersion, Publisher |
Where-Object { $_.DisplayName } |
Sort-Object DisplayName

<img width="752" height="365" alt="image" src="https://github.com/user-attachments/assets/b04d9d50-a9dd-4de3-810b-472e597f3240" />

# Para aplicativos da Microsoft Store
Get-AppxPackage | Select-Object Name, Version

<img width="693" height="437" alt="image" src="https://github.com/user-attachments/assets/38a84104-8bb9-4670-9435-f8e80a244477" />

