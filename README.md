# Export-Filtered-SourceCode-And-Config-Files-Recursively-With-Content

Recursively exports source code, scripts, and configuration files with their contents

---

## 📜 The Command

```powershell
$ts=Get-Date -Format "yyyy-MM-dd_HH-mm-ss"; Get-ChildItem -Recurse -File | Where-Object {$_.Extension -in '.ps1','.psm1','.bat','.cmd','.sh','.py','.js','.mjs','.cjs','.ts','.java','.c','.h','.cpp','.hpp','.cc','.cxx','.cs','.go','.rb','.php','.rs','.swift','.kt','.pl','.json','.yaml','.yml','.xml','.toml','.ini','.cfg','.conf','.env','.md','.markdown','.rst'} | ForEach-Object {"`n===== $($_.FullName) ====="; try { Get-Content $_.FullName -Raw -Encoding UTF8 } catch {}} | Out-File ".\full_src_dump_$ts.txt" -Encoding UTF8
