## SSH
```
$ssh <user>@<host>
$service ssh restart
$echo 'Some Text' | ssh user@host "cat > /remotefile.txt":
```

## Clear pagecache
```
sync; echo 1 > /proc/sys/vm/drop_caches

```

## Clear dentries and inodes
```
sync; echo 2 > /proc/sys/vm/drop_caches
```

## Clear pagecache, dentries and inodes
```
sync; echo 3 > /proc/sys/vm/drop_caches
```

## Disk usage
```
$du -h --max-depth=1
```

## List open files
```
$lsof -u username
$lsof -p pid
$lsof  -u username -c mysql
$lsof -iTCP -sTCP:LISTEN
```

## SCP
```
$scp -r username@servername:/var/www/remotedir /var/www/localdir
$scp -r localdir username@servername:remotedir
```

## Loop
```
$for i in {1..10};do echo $i;done
$while test "1"="1";do echo "test";done
$while :;do echo "test";done
```

## Last exit code
```
$echo $?
```