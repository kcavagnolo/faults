[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/4.0/)

# Setup EC2

Create instance via `awscli` or console. [P2 instances][instance]
using [Deep Learning AMI][dlami] are preferrable for simplicity. Be
sure to configure security group and SSH keys to restrict access to
IP(s).

# Access

Follow the ssh login directions for the instance and activate one of
the default venv configurations:

```bash
$ source activate tensorflow_p36
```

# Setup Jupyter

To access an IDE, one needs to [setup the server][jupyter] first. Then
configure the environment:

```bash
$ pip install jupyter_contrib_nbextensions
$ jupyter contrib nbextension install
$ pip install jupyterthemes
$ jt --theme grade3 -fs 9 -nfs 11 -tfs 11 -cellw 90% -T
```

# Install Tools

For this notebook, library dependencies are short, so no requirements file:

```bash
$ pip install --upgrade numpy pandas scipy featuretools xgboost seaborn scikit-learn tables pyarrow h2o
```			      

# Setup GH Connection

Create keys and add them:
```bash
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
$ ssh-add -K ~/.ssh/id_rsa
$ eval "$(ssh-agent -s)"
```

Got to [GH key settings][keys] and add.

[instance]:https://aws.amazon.com/ec2/instance-types/
[dlami]:https://aws.amazon.com/machine-learning/amis/
[jupyter]:https://docs.aws.amazon.com/dlami/latest/devguide/setup-jupyter-configure-server.html
[keys]:https://github.com/settings/keys
