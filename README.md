# Deep-Learning-Projects

The purpose of this project is to take a dataset containing 382 chorales by Johann Sebastian Bach (in the public domain), where each chorale is composed of 100 to 640 chords with a temporal resolution of 1/16th (ie each chorale is 100 to 640 sixteenth-notes long). Each chord has four notes, composed of 4 integers, each indicating the index of a note on a piano, except for the value 0 which means "no note played."

To get longer notes, chords are repeated (ie, if a chord is repeated twice it is equivalent to an 1/8 note, repeated four times it is equivalent to a quarter note, etc). Note that this doesn't truly represent music as in music you can repeat a note and it means to replay it, not to lengthen its duration. But, this is where we start for this project.

My project does the following:

0.1. Create a sequence-to-sequence RNN that can predict the next chord (4 notes).

0.2. Use 64 chords to train (ie have windows of 64+1, and need to have data in tf.data.Dataset). UseD `Embeddings` to encode each chord (instead of passing note-integers to the RNN).

1. Process my validation set so that I can use it in training the RNN. Then utilize it, and EarlyStopping, and re-train the same RNN from Part 0.2.

2a. Generate music (and not just chords): by feeding the predicted chord along with the previous chords back into the model to predict the next chord, etc. Create a couple new "chorales" utilizing the first chord from chorales in the test set to generate your music. 

3. Listen to my generated music. Convert tokenized chords back into chords and feed them into the player functions in Part 0.1.

4. The music generator tends to "play it safe" and just repeats the same note over and over again. Therefore, I created a temperature, that helps it pick the chord that is the second, third, etc choice according to their respective probabilities and the temperature (how "risky" I want the music generator to be)

USE THIS BY OPENING THE CODE IN GOOGLE COLAB OR A JUPYTER NOTEBOOK AND SELECTING "RUN ALL".
