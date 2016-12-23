# This is a repo for ai club workshop

### Content
* Machine Learning
* Deep Learning

### Start
* Install Docker
* Pull tensorflow image
    ```
    docker pull tensorflow/tensorflow
    ```
* Clone this repo cd to the root directory of the repo
    ```
    git clone git@github.com:sj15291864789/AI-Workshop.git && cd AI-Workshop
    ```
* Start
    ``` 
    docker run -it --rm -p 8888:8888 -v $(pwd)/exercise:/notebooks/ tensorflow/tensorflow
    ```

