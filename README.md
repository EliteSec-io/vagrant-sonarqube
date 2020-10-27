# EliteSec - Sonarqube on Vagrant

This is a simple project for evaluating [Sonarqube](https://www.sonarqube.org/) locally without the need to setup large infrastructure to see if this is the right tool for your needs.  This project includes a [Vagrant](https://www.vagrantup.com/) configuration file that will create an Ubuntu 18.04 LTS virtual machine, install Docker, and then run a docker version of [Sonarqube](https://www.sonarqube.org/) for evaluation.

## Pre-Requisites

* [Virtualbox](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/)
* [SonarScanner](https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/) - _Required if you project's main language is not_ Java, C#, _or_ VB.NET

## Execution

1. Clone this repo
2. Update the plugins via `vagrant plugin update`
3. Execute the command: `vagrant up`
4. Browse to http://localhost:9000/

Further information on how to use Sonarqube, how to scan code, etc, can be found at [Sonarqubes Documentation](https://docs.sonarqube.org/latest/) site.

By default, this setup uses a VM with 4GB of RAM and 2 CPU cores.  You may need to adjust that depending on your needs.

----

Copyright 2020, EliteSec Information Security Consultants, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

----
