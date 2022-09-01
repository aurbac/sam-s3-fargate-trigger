FROM public.ecr.aws/ubuntu/ubuntu:edge

#WORKDIR /usr/src/app

# Copy function code
COPY . .

# Install the function's dependencies using file requirements.txt
# from your project folder.

RUN apt update -y
RUN apt install unzip curl -y
RUN apt install mysql-client -y

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
RUN unzip awscliv2.zip
RUN ./aws/install
RUN aws --version
RUN chmod +x ./bootstrap.sh
ENTRYPOINT ["./bootstrap.sh"]