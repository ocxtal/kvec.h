# kvec.h

Based on [klib](https://github.com/attractivechaos/klib), modified for a simpler style. 2-bit packed vector is also added (as `kpvec_t(type_of_container)`).

## Usage

Ordinary vector

```
#include "kvec.h"
int main() {
	kvec_t(int) array;
	kv_init(array);
	kv_push(array, 10);			// append, kv_push(int, array, 10) in the original impl. in klib
	kv_a(array, 20) = 5;		// dynamic, kv_a(int, a, 20) in klib
	kv_pusha(long, 10);			// push arbitrary sized element, the similar operation as kv_push in klib do
	kv_A(array, 20) = 4;		// static
	kv_destroy(array);
	return 0;
}
```

2-bit packed vector

```
#include "kvec.h"
int main() {
	kpvec_t(int) array;
	kpv_init(array);
	kpv_push(array, 0x02);		// append
	kv_a(array, 20) = 0x01;		// dynamic, kv_a(int, a, 20) in klib
	kv_A(array, 20) = 0x03;		// static
	kv_destroy(array);
	return 0;
}
```


## License

MIT