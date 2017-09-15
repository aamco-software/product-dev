[![Testspace](https://www.testspace.com/img/Testspace.png)](https://www.testspace.com)

***

## Python/Unittest sample for demonstrating Testspace based on the [test_driven_python repo](https://github.com/siddhi/test_driven_python)

Sample demonstrates techniques for using Testspace with Python code and the [`unittest` test framework](https://docs.python.org/2/library/unittest.html) together with [`cov-core` code coverage tool](https://pypi.python.org/pypi/cov-core) and [`nose2` runner](https://github.com/nose-devs/nose2).

  * Using a Testspace Project that is `connected` with this GitHub Repo
  * Using 3 Online CI services for demonstration purposes only
  * Can review the Results at [testspace-samples:python.unittest](https://samples.testspace.com/projects/testspace-samples:python.unittest)  
  * Refer to our [Getting Started](https://help.testspace.com/getting-started) help articles for more information


***
Using Multiple Online CI Services:

[![Build Status](https://travis-ci.org/testspace-samples/php.phpunit.svg?branch=master)](https://travis-ci.org/testspace-samples/python.unittest)
[![CircleCI](https://circleci.com/gh/testspace-samples/python.unittest.svg?style=svg)](https://circleci.com/gh/testspace-samples/python.unittest)
[![Run Status](https://api.shippable.com/projects/5710a3e02a8192902e1c1f8d/badge?branch=master)](https://app.shippable.com/github/testspace-samples/python.unittest)


***
Publishing **Test Content** using www.testspace.com.

[![Space Health](https://samples.testspace.com/spaces/759/badge?token=2b415e73ed35943961c25a0d451ed41da64b029e)](https://samples.testspace.com/spaces/759 "Test Cases")
[![Space Metric](https://samples.testspace.com/spaces/759/metrics/685/badge?token=b4e77a71c198ade1720e3452e1ba684c59d70dde)](https://samples.testspace.com/spaces/759/schema/Code%20Coverage "Code Coverage (lines)")
[![Space Metric](https://samples.testspace.com/spaces/759/metrics/686/badge?token=ed591f894dacb99be130ff1f0a71e7b5a5c58e65)](https://samples.testspace.com/spaces/759/schema/Static%20Analysis "Static Analysis (issues)")

*** 

In order to run this sample you will need a host workstation with installed python 2.6+.

Download and configure the Testspace client 
<pre>
mkdir -p $HOME/bin
curl -s https://testspace-client.s3.amazonaws.com/testspace-linux.tgz | tar -zxvf- -C $HOME/bin
testspace config url samples.testspace.com
</pre>

Buiding:
<pre>
sudo pip install -r requirements.txt
sudo apt-get install pylint
</pre>

Running Static Analysis: 
<pre>
pylint stock_alerter/ -f parseable > analysis.txt
</pre> 

Running Tests with Code Coverage: 

<pre>
nose2 --junit-xml --with-coverage
</pre> 

Push Content using Testspace client

<pre>
testspace analysis.txt{lint} nose2.xml{stock_alerter} coverage.xml 
</pre> 
