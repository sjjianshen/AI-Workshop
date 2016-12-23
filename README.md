# This is a repo for ai club workshop

### Content
* Machine Learning
* Deep Learning

### Start 
* Install Docker
* Pull tensorflow image
    ```
    Docker pull tensorflow/tensorflow
    ```
* Clone this app
    ```
    git clone git@github.com:sj15291864789/AI-Workshop.git
    ```
* Start
    ```
    docker run -it -p 8888:8888 -v $(pwd)/exercise:/notebooks/ tensorflow/tensorflow
    ```

