# Dataset Generator
The dataset of LinGBM is generated by the [BSBM data generator](http://wifo5-03.informatik.uni-mannheim.de/bizer/berlinsparqlbenchmark/spec/BenchmarkRules/index.html#datagenerator).
The original source code of the BSBM data generator can be found [here](https://sourceforge.net/projects/bsbmtools/).

On the basis of the original data generator, we would like to record more statistic data when generating the dataset. These statistic data need to be used for our query generator further.<br>Therefore, we extend some functions in the source code of the BSBM data generator. And the modified code is in the directory: "LinGBM/datasetgen".

### Setup

To generate the dataset, please fistly clone this repo and change to the directory: LinGBM/datasetgen:

```
git clone git@github.com:LiUGraphQL/LinGBM.git
cd LinGBM/datasetgen
```

### Usage

The instruction and command options for using the data generator can be found [here](http://wifo5-03.informatik.uni-mannheim.de/bizer/berlinsparqlbenchmark/spec/BenchmarkRules/index.html#datagenerator). The data generator supports different output format, such as N-Triples, XML, Turtle and SQL dump. 

Here is an example command of generating SQL dataset with the scale factor 1000:

```
java -cp lib/* benchmark.generator.Generator -pc 1000 -s sql
```

You could also use the following example command:

```
./generate -pc 1000 -s sql
```
Note:
In our dataset generator, we disabled the command option '-fc', which means the data generator by default adds one rdf:type statement for the most specific type of a product to the dataset.