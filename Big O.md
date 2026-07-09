In [[programming]], _Big O Notation_ is just seeing how long a function or piece of code scales in performance the more inputs is given to it.

For example:

`O(1)` is a constant, which means it will always be a given speed (or around) no matter the input length.

`O(n)` is slightly different, this is linear. `n` is just the "number of inputs" and it means that the number of total operations (or `O`) scales at a linear compared to the no. of inputs.

Example: if there are `4` inputs and each operation takes 1 second, then it'd take `4` seconds. Now if there were `1,000,000,000` inputs and each operation takes the same amount of time, then it'd take `1,000,000,000` seconds.

`O(2^n)` means for every input, there will be 2 operations to the power of inputs. 

There are also stuff like `O(log n)` which is a good metric as logarithmic growth scales much slower than exponential (i.e `O(n^2)` and much less of factorial `O(n!)`).

See also: [[Python]], [[Bitwise Operations]]