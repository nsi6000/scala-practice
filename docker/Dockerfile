# On Debian, apt-get install podman.
# podman build -t dev .
# podman run -it --rm dev
FROM debian:12 as asd

WORKDIR /home/

RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y curl
RUN apt-get install -y bash
RUN apt-get install -y vim
RUN apt-get install -y git
RUN apt-get install -y openjdk-17-jdk
RUN apt-get install -y clang-format
RUN apt-get install -y gnupg

# From https://www.scala-sbt.org/download/
RUN sh -c 'echo "deb https://repo.scala-sbt.org/scalasbt/debian all main" | tee /etc/apt/sources.list.d/sbt.list'
RUN sh -c 'echo "deb https://repo.scala-sbt.org/scalasbt/debian /" | tee /etc/apt/sources.list.d/sbt_old.list'
RUN sh -c 'curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | apt-key add'
RUN apt-get update
RUN apt-get install -y sbt

RUN git clone https://github.com/nsi6000/scala-practice.git

# RUN sbt new scala/scala3.g8
# RUN sbt compile
# RUN sbt test
# RUN sbt run

COPY ./.vimrc /etc/vim/vimrc

# ENTRYPOINT ["sbt","run"]
