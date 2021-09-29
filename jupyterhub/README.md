## build
    docker build -t anaconda-pyspark .

## run
    docker run -p 8888:8888 -i -t anaconda-pyspark jupyter lab --ip='*' --no-browser