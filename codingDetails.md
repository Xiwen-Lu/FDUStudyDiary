# Oct 14
1. code (Li Sun, IJSAC 2021)
- use fake data to run the network first.
1.1. s means the statement, the size of s is (1,4)
while p is from generator, and q can be got from p.

so, dataloader -> s (1,4)
make a fake function to get q (1,10) from p (the resulet of g()).
besides, dataloader -> q~ (1,10)

1.2. loss F of D and G.

1.3. verify the gradient ascent methods.

1.3. FFT in the train procedure

- read viterbiNet, try to change the fake function.plot

- read End2EndGAN, try to make the dataloader better.plot
