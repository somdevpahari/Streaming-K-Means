# Unsupervised Learning
## Project: Clustering individuals by their income and age
### Install
This project requires [spark](https://www.apache.org/dyn/closer.lua/spark/spark-3.1.2/spark-3.1.2-bin-hadoop3.2.tgz)  and [netcat](https://nmap.org/download.html) installed.

### Background
We're going to start with an machine learning algorithm called K means clustering by using Spark's MLlib library and updating the model in real time as new data is received.
You can imagine it's a sort of model that learns over time in real time, just like a human brain does, given more and more input, you know, as it happens. So the idea of K means clustering is what it sounds like, clustering data. Here, we are clustering data with respect to income and age of individuals.

### Code
The code files are `StreamingKMeans.scala` and `Utilities.scala`. `kmeans-test.txt` and `kmeans-train.txt` are the files which are used for testing and training the model in real time respectively.

### Run
For running the spark code files written in scala, you can use an IDE like [scala IDE](http://scala-ide.org/download/sdk.html). For streaming training and test data using netcat, first open two different terminals and run netcat with

> ncat -kl 9999 < kmeans-train.txt

and

> ncat -kl 7777 < kmeans-test.txt

respectively. After that you run the scala code using IDE. In console of the IDE you will get the real time training and testing output.

### Data
Training data set contains income and age in a vector form required by MLlib library. Test data set contains cluster id followed by income and age in a vector form also.
