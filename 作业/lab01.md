# 配置

## PC0

ip地址

```
10.1.1.2
```

子网掩码

```
255.255.255.0
```

默认网关

```
10.1.1.1
```

## PC1

ip地址

```
30.1.1.2
```

子网掩码

```
255.255.255.0
```

默认网关

```
30.1.1.1
```

## R0

```
no

enable
configure terminal
interface gigabitEthernet 0/0
ip address 10.1.1.1 255.255.255.0
no shu
no shutdown
exit
interface gigabitEthernet 0/1
ip address 20.1.1.1 255.255.255.0
no shu
no shutdown


```

## R1
```
no

enable
configure terminal
interface gigabitEthernet 0/0
ip address 20.1.1.2 255.255.255.0
no shu
no shutdown
exit
interface gigabitEthernet 0/1
ip address 30.1.1.1 255.255.255.0
no shu
no shutdown



```

## R0

```

ip route 30.1.1.0 255.255.255.0 20.1.1.2
ip route 10.1.1.0 255.255.255.0 10.1.1.2
end

show ip route

```

## R1

```

ip route 30.1.1.0 255.255.255.0 30.1.1.2
ip route 10.1.1.0 255.255.255.0 20.1.1.1
end
show ip route
```



























