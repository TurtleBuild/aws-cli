FROM amazon/aws-cli:latest

RUN yum update -y && \
	yum install -y wget unzip java-17-amazon-corretto-devel

ENV JAVA_HOME /usr/lib/jvm/java-17-amazon-corretto.x86_64
ENV GRADLE_HOME /opt/gradle
ENV PATH $JAVA_HOME/bin:$GRADLE_HOME/bin:$PATH

ARG GRADLE_VERSION=7.4.2
ARG GRADLE_DOWNLOAD_SHA256=29e49b10984e585d8118b7d0bc452f944e386458df27371b49b4ac1dec4b7fda

RUN wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" \
	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - \
	&& unzip gradle.zip \
	&& rm gradle.zip \
	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/"

ENTRYPOINT ['sh']