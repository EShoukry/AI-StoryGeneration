# SparkDev AI Team - Story Generation 
## Goal
The goal of this project was to generate comprehensible story campaigns for Dungeons and Dragons (DnD). I was co-lead for the project, and along with one other team member, we attempted to generate paragraphs similar to the ones just below in terms of scope.

![1 goal](https://user-images.githubusercontent.com/35610424/92558701-1c4da980-f23d-11ea-9964-0e44d082f4a4.png)

![2 goal](https://user-images.githubusercontent.com/35610424/92558702-1ce64000-f23d-11ea-9225-146378eb8948.png)

## Data
I had two sets of data that I used for this project. One was a text called "Norwegian Wood", and the other set was locations from the DnD manual. The reason I took two data sets is because I wanted to how different the performance of the model was between something that was trained on more grounded words as opposed to fantastical words found in DnD. The Norwegian Wood text simpler to process due to it being a TXT file ready for me to clean. On the other hand, the DnD manual was a PDF, so I ended up creating a script that used a library in order to parse the PDF into a usable TXT. In addition to that, I had to curate the list to make sure that all the noise (things that weren't parsed properly, spaces, words cut apart, special symbols) was not taken into account when training.  

![story generation data](https://user-images.githubusercontent.com/35610424/92550920-bce69e00-f22a-11ea-8bdc-50647a23e2fc.png)

## The Model
Three models were trained: a bi-directional Long Short-Term Memory RNN to predict the next word in a sentence, a doc2vec model to allow us to vectorize sentences, and a second bi-directional LSTM that would generate descriptions using vectorized sentences from the first LSTM as input. 
![story generation model](https://user-images.githubusercontent.com/35610424/92550922-bd7f3480-f22a-11ea-9d0d-ac6c3378154c.png)

## Results
Although the model did not produce a totally comprehensible output, I was pretty satisfied to see that it learned sentence structure and punctuation, as well as being focused on what the output was supposed to do. There was definitely an attempt to have a conversation in the output on the left, which is trained on the Norwegian Wood text, and it realized that questions marks equal questions as shown by the output. The generation for the location had many descriptors in it, however repetitive. 

![story generation results](https://user-images.githubusercontent.com/35610424/92550924-bf48f800-f22a-11ea-9c31-6473df96eb50.png)

## References
http://deeplearning.net/tutorial/rnnslu.html

https://medium.com/@david.campion/text-generation-using-bidirectional-lstm-and-doc2vec-models-2-3-f0fc07ee7b30
