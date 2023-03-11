FROM ubuntu:20.04

MAINTAINER = Pranav Garg

RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y unoconv imagemagick
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y awscli jq
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y php-fpm php-amqp composer nginx php-imagick

RUN sed -i_bak \
's/rights="none" pattern="PDF"/rights="read | write" pattern="PDF"/' \
/etc/ImageMagick-6/policy.xml

RUN sed -i \
's/name="memory" value="256MiB"/name="memory" value="1GiB"/' \
/etc/ImageMagick-6/policy.xml

RUN sed -i \
'/<policy domain="resource" name="disk" value="1GiB"*/c <!-- <policy domain="resource" name="disk" value="1GiB"/>  -->/' \
/etc/ImageMagick-6/policy.xml

RUN sed -i \
's/name="map" value="512MiB"/name="map" value="756MiB"/' \
/etc/ImageMagick-6/policy.xml