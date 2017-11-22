# SCML Fall 2017 Competition

## BE SURE We get your submission

*Send an email to sito@ucsc.edu to make sure your submission will be judged!!!*

## Can machines learn how the mouse sees?

> The [Santa Cruz Machine Learning Cooperative Cooperative](https://github.com/santacruzml/coop) would like to announce the following challenge, open to the public, to help us push forward our understanding of how visual information is processed in mammals and whether machines can replicate it. This is in collaboration with [SCIPP](http://scipp.ucsc.edu/) (the Santa Cruz Institute for Particle Physics), which develops a device that records from many neurons simultaneously from a live mouse.

* The competition begins on October 5th, 2017 and will end November 26th, 2017 at 11:59PM!

* [Fork this repo](https://github.com/santacruzml/fall-17-scml-competition#fork-destination-box) and open the notebook to get started!

### The Challenge

Your task is to create a model that reproduces visually evoked spiking activity of the neurons in the [superior colliculus](https://en.wikipedia.org/wiki/Superior_colliculus). The superior colliculus is a brain structure, behind the cortex, which is directly connected to the retina. It receives visual, auditory, and [somatosensory](https://en.wikipedia.org/wiki/Somatosensory_evoked_potential) information, combines them together, and sends a motor signal to direct the eyes and head toward an object of an interest. In this competition, we focus on modeling how the visual information is encoded in neuronal activity in the superior colliculus by
predicting the timing of spike trains in response to a stimulus.

### Data

The input data of your model is a short movie that the mouse saw during the experiment; the output data is time series of the firing rates of all the neurons we recorded. As a training dataset, we provide short clips of movies and corresponding firing rates of the neurons.

#### Input data

The original unedited movie is a YouTube video, which can be seen [here](https://www.youtube.com/watch?v=fXNAPBo4dS0). The grayscale version of this movie was presented 6 times during the experiment.

The movie is 290 seconds long, and was divided into 58 five second segments. 48 segments are provided for the training dataset and 10 segments have been randomly removed to later judge the quality of your response.

The provided dataset contains 288 (`48 * 6`) 5 second clips (`150 frames @ 30Hz`, or `33.3ms/frame`) with X-Y pixels already linearized (`128 x 96 -> 12288 pixels`) for training convenience. The movie clips are provided as a 3D `numpy` array (`288 clips x 150 frames x 12288 pixels`). The  [notebook](https://github.com/santacruzml/fall-17-scml-competition/blob/master/scml-SuperiorColliculusCompetition.ipynb) demonstrates how the [release data](https://github.com/santacruzml/fall-17-scml-competition/releases/download/0.0-data/SCNeuronModelCompetition.mat) can be easily loaded.

#### Output data

The output data, which your model attempts to predict, are spiking activity of 54 neurons in the mouse superior colliculus while the mouse watches the movie. The activity of each neuron has been binned using the same time resolution as the movie for convenience. The output
data used for training your model are provided as a 3D numpy array, similar to the movie (`288 clips x 150 frames, x 54 neurons`).

These data can be downloaded from the Github repository of the competition at the
[data release](https://github.com/santacruzml/fall-17-scml-competition/releases/download/0.0-data/SCNeuronModelCompetition.mat).

### Algorithms

Any algorithm is allowed in this competition! You can use the algorithm that you think is best suited for the goal of the competition. Please describe the method either in the comment in the code or documentation of your entry repository.

The notebook is provided
for demonstration or as a basis to begin your modeling effort.

### Other Resources

A similar work has been done using the data from ex-vivo retina combined with convnet based network: [Deep Learning Models of the Retinal Response to Natural Scenes](https://arxiv.org/pdf/1702.01825.pdf). This article may give a good introduction for what type of things we would like to achieve.

If you are in need of GPU resources for entering the competition, and have an active UC login, you may make use of the pattern lab server following [these instructions](https://docs.google.com/a/ucsc.edu/document/d/1DplcVoEhQ-x5D1G-mfIL3Ck_6nOoYLcBdmPArm88dug/edit?usp=sharing).

If you don't have jupyter notebook you can get help installing it [here](http://jupyter.readthedocs.io/en/latest/install.html)!

### Judging Criteria

Your entry will be judged on a variety of criteria.

#### Economy and Resource Consumption

To judge an entry on its ability to use resources effectively, the entry must include details of the computation and resources used to create a response.

#### Brevity and Elegance

Simplicity and explainability are desirable characteristics when working with machine learning results. The interpretability of the model and the complexity of the engineering effort are taken into consideration.

#### Precision and Recall

Entries will be judged on their ability to work with an unseen dataset. Any trained models used should be supplied with the response as well as providing a function that can test new samples.

### How to Enter

To enter a response simply fork this repository to your own github account. Anyone with a github account may submit a response. The tip of the `master` branch November 26, 11:59 PM will be considered your entry. Please make it clear within your code how to direct the model to make predictions from new output data, which will be used by judges to test the precision and recall of your entry.

To fork the repository to your own account, start by clicking the fork icon on github.

<a href="https://github.com/santacruzml/fall-17-scml-competition#fork-destination-box"><img src="https://help.github.com/assets/images/help/repository/fork_button.jpg" /></a>

Then use `git clone https://github.com/YOURACCOUNT/fall-17-scml-competition` to copy the code to your local machine. You can then make modifications and later upload your changes using `git add .`, `git commit -m "my changes"`, `git push origin master`.

* [How to fork a repo](https://help.github.com/articles/fork-a-repo/).
* [Pushing to a remote](https://help.github.com/articles/pushing-to-a-remote/)

### Important dates!

No responses will be accepted after November 26, 11:59 pm. Only commits made before this time will be judged.

All entrants will be contacted that their response is under review by November 29, 11:59 pm.

A list of awards will be given on December 6th at the SCML meeting!

### Get help!

Please join us for the student meetings to get help on formulating an entry! On the November 22nd meeting of the group entrants will have an opportunity to discuss their competition entry and any challenges in submitting.

You can also post your questions to the [github issues](https://github.com/santacruzml/fall-17-scml-competition/issues) or [mailing list](https://groups.google.com/forum/?utm_medium=email&utm_source=footer#!forum/thesmc)!

### Judges

For this challenge these judges have agreed to work with participants to judge the quality of responses. These are subject to change.

<b><a href="https://www.linkedin.com/in/shinya-ito-21297473/">Shinya Ito</a></b>
Postdoctoral Scholar, Santa Cruz Institute for Particle Physics

<b><a href="https://www.linkedin.com/in/rcurrie/">Rob Currie</a></b>
Chief Technical Officer, UCSC Genomics Institute

<b><a href="https://www.linkedin.com/in/david4096/">David Steinberg</a></b>
Bioinformatics Programmer, UCSC Genomics Institute

Judges are expected to use a balance of their expertise and automated methods to judge the quality of a response.

### Prizes

We value work that balances the amount of computational and human effort that goes into a response. All entrants who provide a response by the deadline will receive feedback from our judges and a one-of-a-kind way to remember your effort!

#### Grand Prize
*The entry that best balances human effort, resource consumption, and and accuracy takes the Grand Prize.*

#### Brevity Prize
*The brevity prize is the entry that satisfies the challenge requirements in the fewest lines of written code.*

#### Economy Prize

*The entry that uses the least computational resources, regardless of environment will take the Economy Prize.*

#### Precision Prize

*The entry that achieves the highest accuracy gets the precision prize.*

<hr />

Please [post an issue](https://github.com/santacruzml/fall-17-scml-competition/issues) or send a message to the [mailing list](https://groups.google.com/forum/?utm_medium=email&utm_source=footer#!forum/thesmc) if you have a question!
