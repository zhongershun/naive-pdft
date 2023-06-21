# naive-pdft

***

to compile this porject run command below
```shell
go build naive.go
```

start the master at port 8000
```shell
./naive -role master -maddr:8000
```

in this demo we set f=1 (there is a fault server in this network), so we need t
o start (n = 3f+1) 4 servers.

start four server at port 8001,8002,8003,8004
```shell
./naive -role server -pri pri.pem -pub pub.pem -maddr:8000 saddr:8001
```

finally, start a client at port 8005
```shell
./naive -role client -maddr:8000 -caddr:8005
```

then you can type command in client terminal, you can use operation "get","put"
,"del","all"
```shell
usage: get <key>, put <key> <val>, del <key>, all
```

***

Reference

-[1] Castro M, Liskov B. Practical Byzantine fault tolerance and proactive recovery[J]. ACM Transactions on Computer Systems(TOCS), 2002, 20(4): 398-461.

-[2] Lampotr L. The Part-Time Parliament[J]. ACM Transactions on Computer Systems, 1998,16(2): 133-169.

-[3] Lamport L, Shostak R, Pease M. The Byzantine Generals Problem[J]. ACM Transactions on Programming Languages and Systems, 1982, 4(3): 382-401.
