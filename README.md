# DFTT-Quick
常用 Tips、命令、资源汇总

## 软件
### Avid Media Composer试用期重置
- macOS 终端运行：

```bash
mv "/Library/Application Support/Avid/SWL" "/Library/Application Support/Avid/Licenses" ~/.Trash/ && echo "Avid Media Composer trail reset to 30 days. Open Avid MC. "
```
- Windows CMD 运行:

```cmd
powershell.exe -Command "$s=New-Object -ComObject Shell.Application; $s.Namespace(0).ParseName('C:\ProgramData\Avid\SWL').InvokeVerb('delete'); $s.Namespace(0).ParseName('C:\ProgramData\Avid\Licenses').InvokeVerb('delete'); echo 'Avid Media Composer trial reset to 30 days. Open Avid MC.'"
```
- Windows Powershell 运行:

```powershell
$Shell = New-Object -ComObject Shell.Application

$Shell.Namespace(0).ParseName("C:\ProgramData\Avid\SWL").InvokeVerb("delete") 
$Shell.Namespace(0).ParseName("C:\ProgramData\Avid\Licenses").InvokeVerb("delete") 

Write-Output "Avid Media Composer trial reset to 30 days. Open Avid MC."
```

### Avid Media Composer强制英文界面

如需在非英文语言环境下强制使用英文界面，请运行以下命令将 `English_override.xml` 文件重命名为 `override.xml`：

- macOS 终端运行并输入密码：
```bash
sudo mv "/Applications/Avid Media Composer/SupportingFiles/International/xml/English_override.xml" "/Applications/Avid Media Composer/SupportingFiles/International/xml/override.xml" && echo "Avid Media Composer is now set to English override."
```

- Windows CMD 管理员身份运行：
```cmd
rename "C:\Program Files\Avid\Avid Media Composer\SupportingFiles\International\xml\English_override.xml" override.xml && echo Avid Media Composer is now set to English override.
```

- Windows PowerShell 管理员身份运行：
```powershell
Rename-Item "C:\Program Files\Avid\Avid Media Composer\SupportingFiles\International\xml\English_override.xml" "override.xml"
Write-Output "Avid Media Composer is now set to English override."
```
