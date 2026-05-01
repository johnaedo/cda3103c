---
share_cda3103c: "true"
site-folder: docs/Examples
---

```c
switch (k) {
	case 0: f = i + j;
		break;
	case 1: f = g + h;
		break;
	case 2: f = g - h;
		break;
	case 3: f = i - j;
		break;
}
```

	f: $s0
	j: $s1
	h: $s2
	i: $s3
	j: $s4
	k: $s5

```assembly
.data
jTable: .word L0, L1, L2, L3, Exit

.text

sll $s5, $s5, 2
la $t0, jTable
add $s5, $s5, $t0
jr $s5
L0: add $s0, $s1, $s2
j Exit
L1: add
j Exit
L2: sub
j Exit
L3: sub
j Exit
Exit:
```
