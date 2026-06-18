Normal binary just goes in base2 but with 1 and 0s. 1 = True, 0 = False

As in:

**128,64,32,16,8,4,2,1**

So 5 would just be

Is 5 greater than 128? No, Hence **0**000000

Is 5 greater than 64? No, Hence **00**000000

Is 5 greater than [ ... ]

Is 5 greater than 4? Yes, Hence **000001**00

Then carry the remaining digit (which is 1 since 5 - 4 = 1)

Is 1 greater than 2? No, hence **0000010**0

Is 1 greater than 1? Yes (well, >=), hence **00000101**

Certain stuff can be mentioned in [[Python]]
