# Beam and Python
from [beam.apache.org](https://beam.apache.org/):

# What is it?

An advanced unified programming model

What do I use it for?

To implement batch and streaming data processing jobs that run on any execution engine.

# Some background

## Supercompute vs Clustered Compute

Send all your data to one big giant expensive computer
or
Break up data into teeny tiny pieces and spread it around to lots of computers

So, you want to run on a cluster?

## Step 1: Pick a framework:

Apex
Dataflow
Samza
Nemo
Jet
Hadoop
Spark
Flink
Storm
Sqoop

## Considerations

Differences between frameworks/execution engines:
Spark is in-memory, much faster but can't handle large data.
Map Reduce reads and writes to disk, so it's slower but you wont run out of memory.
Some engines are better at processing streams of data, others better at processing batches, AND MANY MORE!

Or dont think about it too hard and use Beam

## Beam and Runners

"Implement batch and streaming data processing jobs that run on any execution engine."

