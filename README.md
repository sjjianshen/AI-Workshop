# This is a repo for ai club workshop

### Content
* Machine Learning
* BP Neural Network
* Regularization
* Conv Network
* NLP--skip_gram and cbow
* NLP--CNN and LSTM

### Start
* Install Docker
* Clone this repo cd to the root directory of the repo
    ```
    git clone git@github.com:sj15291864789/AI-Workshop.git && cd AI-Workshop
    ```
* Pull tensorflow image
    ```
    docker pull jianshen/tensorflow
    ```
* Start
    ``` 
    docker run -it --rm -p 8888:8888 -v $(pwd)/exercise:/notebooks/ jianshen/tensorflow
    ```
 
Then open your browser and type url http://{your docker machine ip}:8888/?token={the token output in the console}
 
For exercise1, please finish the exercise in ex1_notebook.ipynb, finish the functions that contains todo

### Python and numpy
If you are not familar with python numpy, please refer to this tutorial https://docs.scipy.org/doc/numpy-dev/user/quickstart.html or http://cs231n.github.io/python-numpy-tutorial/


