## 🧨 **PowerShell Commands Cheat Sheet**

#### **1. Delete All Files (Incl. Hidden)**
```powershell
rm -rf ./{*,.*} 2>$null
```
> Dangerous. Deletes all files and folders in current dir — even hidden ones. Think `git clean -xfd` on steroids.

---

#### **2. Recursively Search for a String in Files**
```powershell
Select-String -Path .\* -Pattern "search-term" -Recurse
```
> Like `grep -r` but friendlier. Searches all files under current dir for "search-term".

---

#### **3. Start a Simple HTTP Server (PowerShell 6+)**
```powershell
Start-Process "http://localhost:8080"
```
```powershell
python -m http.server 8080  # (Alt with Python)
```
> Opens the browser and starts a local dev server. Good for static file previews.

---

#### **4. Export a Folder Tree to a Text File**
```powershell
tree /f > structure.txt
```
> Dumps a full folder+file tree into `structure.txt`.

---

#### **5. Show Environment Variables**
```powershell
Get-ChildItem Env:
```
> Lists all environment vars. Use `Env:PATH` to target just one.

---

#### **6. Zip a Folder**
```powershell
Compress-Archive -Path .\MyFolder -DestinationPath MyFolder.zip
```
> Built-in way to zip files without external tools.

---

#### **7. Unzip a File**
```powershell
Expand-Archive -Path MyFolder.zip -DestinationPath .\
```
> Unpacks to current directory.

---

#### **8. Kill a Process by Name**
```powershell
Stop-Process -Name notepad
```
> Like `killall`. Replace `notepad` with anything.

---

#### **9. Get System Info Quickly**
```powershell
Get-ComputerInfo | Out-File sysinfo.txt
```
> Exports detailed system specs. Good for logging or reporting.

---

#### **10. List Listening Ports**
```powershell
Get-NetTCPConnection | Where-Object {$_.State -eq "Listen"}
```
> Shows open ports. Similar to `netstat -an | find "LISTEN"`.

