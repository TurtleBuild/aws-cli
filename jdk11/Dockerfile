FROM amazon/aws-cli:latest

RUN yum update -y && \
	yum install -y wget unzip java-11-amazon-corretto

ENV JAVA_HOME /usr/lib/jvm/java-11-amazon-corretto.x86_64
ENV GRADLE_HOME /opt/gradle
ENV PATH $JAVA_HOME/bin:$GRADLE_HOME/bin:$PATH

ARG GRADLE_VERSION=6.8.3
ARG GRADLE_DOWNLOAD_SHA256=7faa7198769f872826c8ef4f1450f839ec27f0b4d5d1e51bade63667cbccd205

RUN wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" \
	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - \
	&& unzip gradle.zip \
	&& rm gradle.zip \
	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/"

ENTRYPOINT ['sh']