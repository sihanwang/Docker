# Docker

jings-mbp:Docker jing.wang$ docker build -t friendlyhello .
Sending build context to Docker daemon  18.94kB
Step 1/7 : FROM python:2.7-slim
2.7-slim: Pulling from library/python
be8881be8156: Pull complete 
e87541f2e904: Pull complete 
81dc5ba046c8: Pull complete 
b411fa1b92c9: Pull complete 
Digest: sha256:a3ae315a6bc8cd58b4b60bda9eac6640795359b4970230fc5bf4eef3de6a8022
Status: Downloaded newer image for python:2.7-slim
 ---> 42967d04ddc5
Step 2/7 : WORKDIR /app
Removing intermediate container 3c3450fba4e9
 ---> d8280bf0625a
Step 3/7 : ADD . /app
 ---> ccdbbab13543
Step 4/7 : RUN pip install --trusted-host pypi.python.org -r requirements.txt
 ---> Running in 0b8dc8cb8fe6
Collecting Flask (from -r requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/7f/e7/08578774ed4536d3242b14dacb4696386634607af824ea997202cd0edb4b/Flask-1.0.2-py2.py3-none-any.whl (91kB)
Collecting Redis (from -r requirements.txt (line 2))
  Downloading https://files.pythonhosted.org/packages/3b/f6/7a76333cf0b9251ecf49efff635015171843d9b977e4ffcf59f9c4428052/redis-2.10.6-py2.py3-none-any.whl (64kB)
Collecting itsdangerous>=0.24 (from Flask->-r requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/dc/b4/a60bcdba945c00f6d608d8975131ab3f25b22f2bcfe1dab221165194b2d4/itsdangerous-0.24.tar.gz (46kB)
Collecting Jinja2>=2.10 (from Flask->-r requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/7f/ff/ae64bacdfc95f27a016a7bed8e8686763ba4d277a78ca76f32659220a731/Jinja2-2.10-py2.py3-none-any.whl (126kB)
Collecting Werkzeug>=0.14 (from Flask->-r requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/20/c4/12e3e56473e52375aa29c4764e70d1b8f3efa6682bef8d0aae04fe335243/Werkzeug-0.14.1-py2.py3-none-any.whl (322kB)
Collecting click>=5.1 (from Flask->-r requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/34/c1/8806f99713ddb993c5366c362b2f908f18269f8d792aff1abfd700775a77/click-6.7-py2.py3-none-any.whl (71kB)
Collecting MarkupSafe>=0.23 (from Jinja2>=2.10->Flask->-r requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/4d/de/32d741db316d8fdb7680822dd37001ef7a448255de9699ab4bfcbdf4172b/MarkupSafe-1.0.tar.gz
Building wheels for collected packages: itsdangerous, MarkupSafe
  Running setup.py bdist_wheel for itsdangerous: started
  Running setup.py bdist_wheel for itsdangerous: finished with status 'done'
  Stored in directory: /root/.cache/pip/wheels/2c/4a/61/5599631c1554768c6290b08c02c72d7317910374ca602ff1e5
  Running setup.py bdist_wheel for MarkupSafe: started
  Running setup.py bdist_wheel for MarkupSafe: finished with status 'done'
  Stored in directory: /root/.cache/pip/wheels/33/56/20/ebe49a5c612fffe1c5a632146b16596f9e64676768661e4e46
Successfully built itsdangerous MarkupSafe
Installing collected packages: itsdangerous, MarkupSafe, Jinja2, Werkzeug, click, Flask, Redis
Successfully installed Flask-1.0.2 Jinja2-2.10 MarkupSafe-1.0 Redis-2.10.6 Werkzeug-0.14.1 click-6.7 itsdangerous-0.24
You are using pip version 10.0.1, however version 18.0 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
Removing intermediate container 0b8dc8cb8fe6
 ---> 24c9e3f704ff
Step 5/7 : EXPOSE 80
 ---> Running in 34b6427452b1
Removing intermediate container 34b6427452b1
 ---> a5e06c12e423
Step 6/7 : ENV NAME World
 ---> Running in b4c77e53d169
Removing intermediate container b4c77e53d169
 ---> 4c19f46e719a
Step 7/7 : CMD ["python", "app.py"]
 ---> Running in 9ec487c5e049
Removing intermediate container 9ec487c5e049
 ---> 383f5863603d
Successfully built 383f5863603d
Successfully tagged friendlyhello:latest
jings-mbp:Docker jing.wang$ docker image ls
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
friendlyhello       latest              383f5863603d        6 minutes ago       132MB
python              2.7-slim            42967d04ddc5        6 days ago          120MB
hello-world         latest              2cb0d9787c4d        12 days ago         1.85kB
