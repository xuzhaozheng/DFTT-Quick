# DFTT-Quick
常用 Tips、命令、资源汇总

## 软件
### Avid Media Composer试用期重置
- macOS 终端运行：

```
mv "/Library/Application Support/Avid/SWL" "/Library/Application Support/Avid/Licenses" ~/.Trash/ && echo "Avid Media Composer trail reset to 30 days. Open Avid MC. "
```
- Windows CMD 运行:

```
powershell.exe -Command "$s=New-Object -ComObject Shell.Application; $s.Namespace(0).ParseName('C:\ProgramData\Avid\SWL').InvokeVerb('delete'); $s.Namespace(0).ParseName('C:\ProgramData\Avid\Licenses').InvokeVerb('delete'); echo 'Avid Media Composer trial reset to 30 days. Open Avid MC.'"
```
- Windows Powershell 运行:

```
$Shell = New-Object -ComObject Shell.Application

$Shell.Namespace(0).ParseName("C:\ProgramData\Avid\SWL").InvokeVerb("delete") 
$Shell.Namespace(0).ParseName("C:\ProgramData\Avid\Licenses").InvokeVerb("delete") 

Write-Output "Avid Media Composer trial reset to 30 days. Open Avid MC."
```
