# Traffic
### Blaze Halderman

#### Process - Experimenting
* I started out with a single convolution layer of 32 filters using a 3 x 3 kernal, a maxpooling layer using 2 x 2 pool size, 1 hidden layer using 128 nodes and a 0.5 dropout -> [0.0556]

* I then started testing by changing the maxpool size to a 3 x 3 -> [0.0547]

* I reverted the changes, and added double of everything(convolution layer, maxpooling layer, flatten) -> [0.9688]

* I reverted the changes, and then added just 1 more convolution layer with 64 filters using a 3 x 3 kernal -> [0.9774]

* I reverted the changes, and added double of everything with one convolution layer with 64 filters using a 3 x 3 kernal -> [0.0532]

* I reverted the changes, and then added 2 more convolution layers with 32 filters using a 3 x 3 kernal -> [0.9713]

#### Process - Conclusion
I tried various methods to get positive and consistent results, and the method which seemed to work best was adding a single convolution layer of 32 filters using a 3 x 3 kernal, a maxpooling layer using 2 x 2 pool size, 1 hidden layer using 128 nodes and a 0.5 dropout, and 1 more convolution layer with 64 filters using 3 x 3 kernal with a resulting accuracy of `0.9774` and a loss of `0.1491`, which is amazing in my opinion! What didn't work well was when I tried adding more then a single convolution layer of a single type, for example having two convolution layers of the same filters and then adding another with 64, resulting in no progress and actually went backwards often times in the results. Then when I tried with 2 convolution layers on top of the single 32 layer already implemented(total 3) I got `0.9713`, which is also great! I think what makes the most sense to me is adding a convolution layer with 64 filters using a 3 x 3 kernal since we want to continue to add more filters as the algorithm progresses, making it better for the neural network to calculate values. During the first `Epoch (Epoch 1)` it already had an accuracy of `0.3601` and then the second `Epoch (Epoch 2)` had an accuracy of `0.8410` which is a massive jump! The only methods which results is strange results were my original plan, changing the max pool size with the original plan, and adding double of everything with one of the layers being a 64 filter using 3 x 3 kernal.