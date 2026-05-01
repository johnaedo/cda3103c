---
share_cda3103c: "true"
site-folder: site/Examples
---

C Code
*Loops through an array and multiplies the value by 2*
```c
int A[15];
for (i = 0; i < 15; i++) {
	A[i] = A[i] * 2;
}
```

Assembly Code
A is array of integers, i.e. array of 4-byte Thingies
Base address of A is in $s1
Index i is in $s2

```asm
		addi $s2, $s2, 0        # i = 2
loop:   slti  $t0, $s2, 15
		beq   $t0, $zero, exit
		sll   $t1, $s2, 2       # offset = i * 4
		add   $t2, $s1, $t1     # access address = base + offset
		addi  $s2, $s2, 1
		lw    $t3, 0($t2)
		sll   $t3, $t3, 1
		sw    $t3, 0($t2)
		j loop
exit:

```