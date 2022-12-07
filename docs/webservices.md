# Getting started with programmatic access

Job Dispatcher provides programmatic access to data resources and analysis tools via Web Services technologies,
which are built on open standards, such as:

- Representational state transfer (REST): a software architecture style.

- Hypertext Transfer Protocol Secure (HTTPS): an application-layer protocol for transmitting data.

[//]: # (- Simple Object Access Protocol &#40;SOAP&#41;: a messaging protocol for transporting information.)

[//]: # (- Web Services Description Language &#40;WSDL&#41;: a method for describing Web Services and their capabilities.)


## Fair usage

We kindly ask all users of Job Dispatcher services to submit jobs **in batches of no more
than 30 at a time and not to submit more until the results and processing are complete**.

!!! warning

    We kindly ask all users of EMBL-EBI Web Services to submit tool jobs **in batches of no more 
    than 30 at a time and not to submit more until the results and processing is complete**. 
    Please ensure that a valid email address is provided. Excessive usage of a particular 
    resource will be dealt with in accordance with [EMBL-EBI's Terms of Use](http://www.ebi.ac.uk/about/terms-of-use). 
    Please [contact us](https://www.ebi.ac.uk/support/webservices) if you need further information.
    
    Chinese / 中文

    敬告所有 EMBL-EBI Web Services 网络服务用户，请在呈交工具工作时，每批工作 不要超过30项，
    并请您在该批数据的结果和处理程序完成之后再呈交下一批工作。并请您提供一个有效的电子邮件地址。
    超额使用某项资源将按照 [EMBL-EBI使用条款处理。](http://www.ebi.ac.uk/about/terms-of-use) 如需进一步信息，
    请通过此链接 [与我们联系。](https://www.ebi.ac.uk/support/webservices)
    
    Korean / 한글
    
    EMBL-EBI 웹서비스는 다량의 데이터(배치 등) 호출시, 사용자당 실시간으로 최대 30건의 처리를 제한적으로 사용하실 것을 권고드리고 있습니다. 
    보내신 건이 완료되기 전에, 재차 더 많은 데이터가 전송되지 않도록 협조 부탁드립니다.
    또한 유효한 메일주소를 사용해주시기 바랍니다. 다량의 데이터 사용에 관한, 
    [EMBL-EBI 이용 약관](http://www.ebi.ac.uk/about/terms-of-use)을 준수해 주실것을 부탁드리며, 관련해 도움이 필요하시면, 
    [문의](https://www.ebi.ac.uk/support/webservices) 주시기 바랍니다.


## OpenAPI

The [OpenAPI Specification](https://swagger.io/specification/), 
previously known as the Swagger Specification, is a specification for a 
machine-readable interface definition language for describing, 
producing, consuming and visualizing RESTful web services.

We provide OpenAPI [Swagger User Interface (UI)](https://www.ebi.ac.uk/Tools/common/tools/help/), 
that you can use to explore the Job Dispatcher API and try its various endpoints.

## Clients

Example command-line (CLI) clients, are provided for Job Dispatcher RESTful APIs. 
These are provided in a number of programming languages, namely Python, Perl and Java.
Instructions on how to download the clients and how to use them are provided in the clients' 
[GitHub repository](https://github.com/ebi-jdispatcher/webservice-clients).

These clients are generated from the APIs directly with a Python application
[webservice-clients-generator](https://github.com/ebi-jdispatcher/webservice-clients-generator).

### Running the clients

[Download](https://github.com/ebi-wp/webservice-clients/archive/master.zip) the clients or clone the repository:


``` py title="Clone the repository"
git clone https://github.com/ebi-wp/webservice-clients.git
```
#### Perl clients

In order to run Perl clients, Perl (tested version 5.22.0) needs to installed as well as Perl dependencies. 
Install dependencies with:

``` py title="To install Perl dependencies run (you might need sudo)"
cpan LWP
cpan XML::Simple
cpan YAML::Syck
```

``` perl title="An example test for Clustal Omega Perl client"
perl clustalo.pl --email <your@email.com> --sequence sp:wap_rat,sp:wap_mouse,sp:wap_pig
```

#### Python clients

Specially if you have no root access to your machine, you might need to use virtualenv. Prepare a virtual environment where all the Python (tested version 3.6.5) dependencies will be installed.

``` py
virtualenv -p `which python` env
source ./env/bin/activate
```

``` py title="Install dependencies with"
pip install --upgrade pip xmltramp2 requests
```

``` py title="An example test for Clustal Omega Python client"
python clustalo.py --email <your@email.com> --sequence sp:wap_rat,sp:wap_mouse,sp:wap_pig
```

#### Java clients

In order to run Java clients, OpenJDK 8 (tested version 1.8.0_161") as well as ant (tested version 1.10.5), needs to installed. Note OpenJDK 9 and above are currently not supported.
The clients are provided here as self-contained JAR files. (The source code is available in the [webservice-clients-generator repository](https://github.com/ebi-wp/webservice-clients-generator)). 
To run them on all platforms, an example for the Clustal Omega Java client is:
``` java
java -jar clustalo.jar --email <your@email.com> --sequence sp:wap_rat,sp:wap_mouse,sp:wap_pig
```

On Linux and OSX you can use the simpler:

``` java 
./clustalo.jar --email <your@email.com> --sequence sp:wap_rat,sp:wap_mouse,sp:wap_pig
```
## Docker

[Docker](https://www.docker.com/) is a set of platform as a service product that use OS-level virtualization 
to deliver software in packages called containers

We provide a Docker container with all our example clients pre-installed. 
To learn to pull our Docker image and run the clients with Docker refer to the information provided in our
[GitHub repository](https://github.com/ebi-jdispatcher/webservice-clients).

## CWL

The [Common Workflow Language](https://www.commonwl.org/) 
is a standard for describing computational data-analysis workflows.

In addition to these clients uwe provide example Common Workflow Language (CWL) tool definitions as well as
example CWL workflows. 
To learn more about CWL and how to use them please refer to the information provided in our
[GitHub repository](https://github.com/ebi-jdispatcher/webservice-cwl).

## Dbfetch

[Dbfetch](https://www.ebi.ac.uk/Tools/dbfetch/) provides a common interface to database entry retrieval 
in a variety of different formats.
Example clients and CWL files are provided for programmatically accessing Dbfetch. 

Additional information on how to retrieve entries from Dbfetch programmatic is provided on the
[Dbfetch URL Synthax](https://www.ebi.ac.uk/Tools/dbfetch/syntax.jsp) page.


