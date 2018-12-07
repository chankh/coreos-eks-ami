FROM python:2

RUN apt-get update \
 && apt-get install -y groff \
 && apt-get clean autoclean \
 && apt-get autoremove --yes \
 && rm -rf /var/lib/{apt,dpkg,cache,log}/ \
 && pip install --upgrade awscli \
 && curl -LO https://s3.amazonaws.com/cloudformation-examples/aws-cfn-bootstrap-latest.tar.gz \
 && tar -zxf aws-cfn-bootstrap-latest.tar.gz \
 && cd aws-cfn-bootstrap-1.4 \
 && python setup.py install \
 && ln -s `pwd`/aws-cfn-bootstrap-latest/init/ubuntu/cfn-hup /etc/init.d/cfn-hup