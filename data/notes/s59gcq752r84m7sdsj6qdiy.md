

- [[s.apps.azure.devops]] Extension for [Automatic Release Notes](https://marketplace.visualstudio.com/items?itemName=richardfennellBM.BM-VSTS-XplatGenerateReleaseNotes&ssr=false#overview)
- [[s.q.tsql]] [[s.q.tsql.tools.redgate]] [Version Control Demo With Git](https://youtu.be/mNXipSFbV0s)
  - [[s.apps.vscode]] `https://github.com/microsoft/codetour` Code Tours to walk users through a code base
  - [[s.l.bash]] `printenv` prints out all current environmental variables
  - [[s.l.powershell]]
  - Making a powershell module i had to save the script file as a `.psm1` to the `$PSModulePath` which didnt work initially so i instead passed an absolute path for module import:

```powershell
Import-Module -Name 'C:\PathToModule' -Verbose
```

- To utilize non-ascii characters to get the script to print output like the `tree` command i had to open the file in Notepad++ and convert the encoding to `utf8-BOM` for `Byte Order Mark` weird shenanigans
  - _Related Links:_
    - https://stackoverflow.com/questions/14482253/utf8-script-in-powershell-outputs-incorrect-characters
    - https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_character_encoding?view=powershell-7.1
    - https://docs.microsoft.com/en-us/powershell/scripting/developer/module/modifying-the-psmodulepath-installation-path?view=powershell-7.1
    - https://docs.microsoft.com/en-us/powershell/scripting/developer/module/importing-a-powershell-module?view=powershell-7.1
    - https://ss64.com/ps/import-module.html#:~:text=To%20import%20the%20module%20into,PowerShell%20modules%20in%20the%20PSSession.
      - Ultimately to get a version of [This Script replicating the tree command](https://www.powershellgallery.com/packages/Show-Tree/1.0.0/Content/Show-Tree.ps1) but with modifications so that it uses the non-ascii characters that the `tree` command used
