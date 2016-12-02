Overview
============
This code will reword an input phrase from the user using Google's Parsey McParseface parser. More information can be found in the [original repo](https://github.com/tensorflow/models/tree/master/syntaxnet). This the code for 'Build an AI Reader' on [Youtube](https://youtu.be/AKwfVAKaigI)

Dependencies
============

* Python 2.7 - (https://www.python.org/downloads/)
* bazel - First do this in Ubuntu 16.04 instructions [here](http://bazel.io/docs/install.html)
* `wget https://storage.googleapis.com/bazel-apt/doc/apt-key.pub.gpg`
* `sudo apt-key add apt-key.pub.gpg`
* `sudo apt-get install pkg-config zip g++ zlib1g-dev unzip`
* `sudo add-apt-repository ppa:webupd8team/java`
* `sudo apt-get update`
* `sudo apt-get install openjdk-8-jdk`
* `sudo apt-get install oracle-java8-installer`
* `export PATH="$PATH:$HOME/bin"`
* Download the Bazel installer for your operating system.
* `wget https://github.com/bazelbuild/bazel/releases/download/0.4.1/bazel-0.4.1-installer-linux-x86_64.sh`
* `chmod +x bazel-0.*`
* `./bazel-version-installer-os.sh --user`
* install [brew](http://linuxbrew.sh/)
* swig `brew install swig`
* protobuf `sudo pip install -U protobuf==3.0.0b2`
* asciitree `sudo pip install -U protobuf==3.0.0b2`
* numpy `sudo pip install numpy`

Use [pip](https://pypi.python.org/pypi/pip) to install any missing dependencies

Basic Usage
===========

Step 1 - Build from source 

```shell
  cd syntaxnet/tensorflow
  ./configure
  cd ..
  bazel test syntaxnet/... util/utf8/...
  # On Mac, run the following:
  bazel test --linkopt=-headerpad_max_install_names \
    syntaxnet/... util/utf8/...
```
Step 2 - Run the demo class with an input phrase of your choice 

```shell
cd syntaxnet
python test.py find me a restaurant in san francisco
```

Sample output: 
```shell
Intent is: discover restaurant
```

Credits
===========
Credit for the vast majority of code here goes to [The SyntaxNet team at Google](https://github.com/tensorflow/models/edit/master/syntaxnet). I've merely created a wrapper around some of the important functions to get people started.
