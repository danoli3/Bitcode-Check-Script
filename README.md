# Bitcode-Check-Script
Check your libraries if they have Bitcode embedded

Use this script to determine if libraries contain bitcode embedded code


### Usage: ```bitcodeCheck "boost_system.a" ```

Results:
```
------------------
BITCODE=YES for: boost_system.a
------------------
```


For a archive that is not bitcode, it will return ```BITCODE=NO```
