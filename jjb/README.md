

To update jenkins jobs via jjb we must first install the
``jenkins-jobs`` executable:

```
# dnf install /usr/bin/jenkins-jobs
```

Then we must put our credentials and the jenkins endpoint in
a cfg file that can be used:

```
# cat <<EOF > jenkins_jobs.ini
[jenkins]
user=username
password=password
url=https://ci.centos.org
EOF
```

Edit the username and password in the file to be your username
password for jenkins.

Finally we can run `jenkins-jobs` to update the jobs. In our 
case our job is defined in a `job.yaml` file. Run the following
command to upate the jobs in jenkins:

```
# jenkins-jobs --conf jenkins_jobs.ini update job.yaml
```
