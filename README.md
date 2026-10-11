# Full Source Dump

Recursively exports source code, scripts, and configuration files with their contents

---

## 📜 The Command

```powershell
$ts=Get-Date -Format "yyyy-MM-dd_HH-mm-ss"; Get-ChildItem -Recurse -File | Where-Object {$_.Extension -in '.bat','.c','.cc','.cfg','.cmd','.conf','.cpp','.cs','.cjs','.cxx','.env','.go','.h','.hpp','.html','.ini','.java','.js','.json','.kt','.mjs','.md','.markdown','.php','.pl','.ps1','.psm1','.py','.rb','.rs','.rst','.sh','.swift','.toml','.ts','.xml','.yaml','.yml'} | ForEach-Object {"`n===== $($_.FullName) ====="; try { Get-Content $_.FullName -Raw -Encoding UTF8 } catch {}} | Out-File ".\full_src_dump_$ts.txt" -Encoding UTF8


