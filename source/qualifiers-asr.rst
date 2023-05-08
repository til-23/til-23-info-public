Qualifiers - ASR
~~~~~~~~~~~~~~~~

What is the ASR Challenge about?
#################################


* The dataset consists of speech audio clips with utterances of a few seconds per clip and their corresponding transcriptions.
* The datasets given will **only** be in **English**. Majority of the datasets given are in the intonation of Singapore English.
* Your task is to train a model to perform **speech recognition** (also known as speech-to-text).
* You will be provided a training set for your use. You are allowed to include additional data to train your model, terms & conditions apply (refer to “Important rules for participants” below for more information).
* A separate test dataset will be released and you are supposed to evaluate your model using this test dataset which **will** be used as a judging criteria for the qualifiers.


File format of the dataset - How are the files given to you?
############################################################

* Training set
    * The audio clips will be given in .wav format, mono, with a sampling rate of 16,000 Hz.
    * The given annotations will be in **CAPS** form.
    * Only these characters are used in forming the annotations, and you are expected to only produce the transcription using these characters. These characters are:
        A B C D E F G H I J K L M N O P Q R S T U V W X Y Z <SPACE>
    * The annotations will be given in .csv format, with the following structure:


.. list-table:: Train.csv
	:widths: 25 50 25
   	:header-rows: 0
   	
   	* - path
   	  - annotation
   	  -
   	* - audio/train_00001.wav
   	  - AUDIO TRANSCRIPTION FOR CLIP ONE
   	  -
   	* - audio/train_00002.wav
   	  - AUDIO TRANSCRIPTION FOR CLIP TWO
   	  -
   	* - audio/train_00003.wav
   	  - AUDIO TRANSCRIPTION FOR CLIP THREE
   	  -
   	* - ...
   	  - ...
   	  -


* Interim and Evaluation set
    * The audio clips will be given in .wav format, mono, with a sampling rate of 16,000 Hz.
    * If your team is in the advanced tier, the test set audio files will begin with the "evala\_" prefix. If your team is in the novice tier, the test set audio files will begin with the "evalb\_" prefix.
    * A .csv file containing all the file path of the audio clips will be given with the following structure:


.. list-table:: Test_{Advanced, Novice}.csv
	:widths: 50 25
   	:header-rows: 0
   	
   	* - path
   	  -
   	* - audio/eval{a,b}_00001.wav
   	  -
   	* - audio/eval{a,b}_00002.wav
   	  -
   	* - audio/eval{a,b}_00003.wav
   	  -
   	* - ...
   	  - 

Boilerplate Code
#################

* An end-to-end boilerplate code will be given to you, together with a code walkthrough video on a **demo dataset**. Please find the code that will be released together with the dataset and the video in the training videos.

Evaluation - How will the ASR Challenge be evaluated?
#####################################################

* The ASR challenge will be evaluated with the Word Error Rate (WER) metric. You can read up further on the `Definition of WER <https://sonix.ai/articles/word-error-rate>`_. WER is computed with the following equation below:

::

    # S: Number of substitutions
    # D: Number of deletions
    # I: Number of insertions
    # N: Number of words in the reference

    WER = (S + D + I) / N

Submission - How to submit your final evaluation?
#################################################

* The submission format will be the standard CSV format. Please ensure that the submissions are in .csv with format matching the following structure as shown below:
    
.. list-table:: submission.csv
	:widths: 25 50 25
   	:header-rows: 0
   	
   	* - path
   	  - annotation
   	  -
   	* - eval{a,b}_00001.wav
   	  - PREDICTED TRANSCRIPTION FOR FILENAME ONE
   	  -
   	* - eval{a,b}_00002.wav
   	  - PREDICTED TRANSCRIPTION FOR FILENAME TWO
   	  -
   	* - eval{a,b}_00003.wav
   	  - PREDICTED TRANSCRIPTION FOR FILENAME THREE
   	  -
   	* - ...
   	  - ...
   	  -
    
* Take note that the csv file can only have 2 columns, with column header "path" and "annotation"
* Refer to the boilerplate code to see how the submission file is being generated.

Additional rules for participants
#################################

* You need not necessarily use the boilerplate code and can write your own model code for the competition. Any form of deep learning techniques are fine i.e supervised, semi-supervised or self-supervised method, including loading of pretraining models.
