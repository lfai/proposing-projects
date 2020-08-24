==DELTA Project Proposal

*Name of the project*: DELTA

*Requested maturity level*: Incubation

*Description*

**DELTA** is a deep learning based end-to-end **natural language and speech processing** platform. DELTA aims to provide easy and fast experiences for using, deploying, and developing natural language processing and speech models for both academia and industry use cases. DELTA is mainly implemented using TensorFlow and Python 3.

*Possible integrations with existing LF DL projects:* None

*License*: Apache License 2.0

*Source control*: https://github.com/didi/delta

*External dependencies*:

Depends on:

  * [Tensorflow](https://github.com/tensorflow/tensorflow), Apache-2.0 License
* [abseil-cpp](https://github.com/abseil/abseil-cpp), Apache-2.0 License
* https://github.com/google/protobuf, https://github.com/protocolbuffers/protobuf/blob/master/LICENSE
* https://github.com/google/googletest,  BSD-3-Clause License
* https://github.com/google/sentencepiece, Apache-2.0 License
* https://github.com/applenob/cppjieba.git, None
* https://github.com/jbeder/yaml-cpp.git, MIT License
* https://github.com/open-source-parsers/jsoncpp.git, MIT License
* https://github.com/ARMmbed/mbedtls.git, Apache-2.0 License
* https://github.com/curl/curl.git, https://github.com/curl/curl/blob/master/COPYING
* https://github.com/HISONA/https_client, Apache-2.0 License

Includes code from:

* https://github.com/JianGoForIt/YellowFin, Apache-2.0 License
* https://github.com/tensorflow/lingvo, Apache-2.0 License
* https://github.com/tensorflow/tensor2tensor, Apache-2.0 License
* https://github.com/jameslyons/python_speech_features, MIT License
* https://github.com/kaldi-asr/kaldi, Apache-2.0 License
* https://github.com/srvk/eesen, Apache-2.0 License
* https://github.com/espnet/espnet, Apache-2.0 License

*Initial committers:*

  * Kun Han, kunhan@didiglobal.com, DIDI, Since Aug 2019;
  * Hui Zhang, ethanzhanghui@didiglobal.com, DIDI, Since Aug 2019;
  * Junwen Chen, chenjunwen@didiglobal.com, DIDI, Since Aug 2019;
  * Haiyang Xu, xuhaiyangsnow@didiglobal.com, DIDI, Since Aug 2019;


*Infrastructure requests:*
In order to facilitate external development, we need to make it easy for anyone to run integration
tests. Currently, we’re using Travis CI for integration tests which provides CPU tests only. There has
been a number of issues where only GPU components failed, while CPU tests were passing.
This forces developers to run integration tests on GPU boxes manually.
We’d like to make use of LF continuous integration environment and request a GPU support.

*Current mailing lists:*
None, we will request LF to create lists for users, developers, and TSC.

*Resources:*

  * Issue tracker - https://github.com/didi/delta/issues
  * CI - https://travis-ci.org/github/didi/delta
  * DockerHub - https://hub.docker.com/repository/docker/zh794390558/delta
  * Docs - https://delta-didi.readthedocs.io/

*Website:*
None.

*Release methodology & mechanics:*
The release is performed when committers pass the vote to do so. 

The release procedure is as follows:

  * Verify that Travis CI tests are passing.
  * Publish docker image to DockerHub.

*Social media accounts:*
None.

*Existing sponsorship:*
None.

*CII Best Practices Badge:*
None.