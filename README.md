# MSSQL-mdf-file-dump

MSSQL store creds in a master.mdf file. If we managed to get that file, we can extract the hashes from mdf file.

# Extract Hashes from mdf file

![OnPaste 20220609-182026](https://user-images.githubusercontent.com/106917304/172851000-e5b1f130-0ead-4633-8c4c-626100bcfddd.png)


### Open Powershell in Kali VM.
![OnPaste 20220609-182203](https://user-images.githubusercontent.com/106917304/172851320-19cffbc0-4b97-4e3f-b2e6-b74bb183d410.png)


Grab   Get-MDFHashes.ps1 / OrcaMDF.RawCore.dll / OrcaMDF.Framework.dll

[Resource](https://github.com/xpn/Powershell-PostExploitation/tree/master/Invoke-MDFHashes)


### Import the Modules 
```markdown
Add-Type -Path 'OrcaMDF.RawCore.dll' 
Add-Type -Path 'OrcaMDF.Framework.dll' 
import-module .\Get-MDFHashes.ps1 
```
NOTE: If Get-MDFHashes.ps1 shows error on running run twice like i did.

![OnPaste 20220609-182705](https://user-images.githubusercontent.com/106917304/172852863-797391a1-e40e-4992-af8f-8b4dfd265610.png)


### Dump THe Hashes
```markdown
Get-MDFHashes -mdf "/home/kali/dump/master.mdf" 
```
NOTE: You have to provide the full path to master.mdf file.

![OnPaste 20220609-183727](https://user-images.githubusercontent.com/106917304/172854470-622a959a-6b47-44aa-ada4-00b2802c4e4c.png)

These value are the hash.
You will notice that hash don't fit in our screen. To make the hash visible we have to change our resolution.
In Kali.

First use to see the default. 
```markdown
xrandr 
```

```markdown
xrandr -s 3840x2400 
```
Now again dump the Hash. It's inconventient to work like this, so grab the hash and copy to a file. Then change the resolution to default. Now try to crack the hash. 

![OnPaste 20220609-184608](https://user-images.githubusercontent.com/106917304/172856147-995b5d5a-c9d5-4503-879e-5f6df977c42e.png)


![OnPaste 20220609-184834](https://user-images.githubusercontent.com/106917304/172856660-a7b1b41f-2ec2-476c-9ab8-1cc42af55217.png)



