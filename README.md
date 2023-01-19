# opcodes-and-operations

# Modulo By 2 A Given Input n

All the code below is used to simply do: `input % 2` & return the result

## Runtime Code

```
60 PUSH1 0x04 // save input in memory
35 CALLDATALOAD
60 PUSH1 0x00
52 MSTORE // mstore(0, calldataload(4))
60 PUSH1 0x02
60 PUSH1 0x00
51 MLOAD
06 MOD // mod((mload(0), 2)
60 PUSH1 0x00
52 MSTORE // override memory at index 0 to store modulo result
60 PUSH1 0x20
60 PUSH1 0x00
F3 RETURN // return input from memory at index 0 on 32 bytes (0x20)
```

Concatenation of 20 bytes from above: 60043560005260026000510660005260206000f3

## Creation Code

```
73 PUSH20 0x60043560005260026000510660005260206000f3
60 PUSH1 0x00
52 MSTORE
60 PUSH1 0x14 // 20 bytes long
60 PUSH1 0x0c // 12 bytes offset
F3 RETURN
```

Concatenation of instructions above: 7360043560005260026000510660005260206000f36000526014600cf3
