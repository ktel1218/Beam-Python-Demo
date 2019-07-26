# Apache Beam - Python

# Apache Beam
__from [beam.apache.org](https://beam.apache.org/)__

What is it?
: An advanced unified programming model

What do I use it for?
: To implement batch and streaming data processing jobs that run on any execution engine.

# Some background

### You have a lot of data, and you want to do something to it.

# Supercompute vs Clustered Compute

Send data to one big giant expensive computer

**or**

Break up data into pieces and send to lots of computers (a cluster).

# Do you have a supercomputer?
### Yes/No

# Lets use a cluster.

#### Step 1: Pick a framework:

* Apex
* Dataflow
* Samza
* Nemo
* Jet
* Hadoop
* Spark
* Flink
* Storm ... etc


# Considerations

* in-memory?
* on disk?
* streaming?
* batching?
* microbatching?
* querying?
* machine learning?
* guarantees?
* platform-specific?
* ... etc

# Another Option

### Dont think about it too hard and use Beam

# Parallels

### Sqlalchemy

###[Discuss]

# Question Break

# Real-World Scenario

(kind of)

Run:

`python clean_numbers_complete.py --input phone-numbers.txt --output output.txt`

Check output.

Modify clean_numbers.py to get a similar (or improved!) version of the output file we just saw.

# Potential Enhancements

### [Discuss]

# Other Potential Enhancements

1. GroupBy Area Code and Count (see [the core transforms library](https://github.com/apache/beam/blob/master/sdks/python/apache_beam/transforms/core.py) for ideas of what to use instead of beam.Map)
4. Add metrics ([example in original wordcount code](https://github.com/apache/beam/blob/master/sdks/python/apache_beam/examples/wordcount.py))
2. Turn it into a streaming app by replacing ReadFromText with ReadFromPubSub and WriteToText with WriteToPubSub ([example streaming wordcount code](https://github.com/apache/beam/blob/master/sdks/python/apache_beam/examples/streaming_wordcount.py))
3. Pass in a different runner with the `--runner` arg, such as DataflowRunner (will require additional arguments)
5. Find out how to run in parallel (spin up a kubernetes cluster locally!). Include a timer in your metrics, and see if that speeds things up or slows things down.

