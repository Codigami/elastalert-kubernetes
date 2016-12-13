
# What does it do ?
Elastalert is used for alerting on unknown scenario in our production environment based on predefined rules of different types of alerts in the rules config file. 

# How to create new alerts. 

Add a new rules file in the rules directory. More information about different types of rules [here](http://elastalert.readthedocs.io/en/latest/elastalert.html#overview). Once elastalert detects changes in any file, it reloads the applications. 

# How to create docker file
e.g. ```docker build -t elastalert:1.0 .```

# How to run elastalert in docker
When running elastalert for the very first time, ```elastalert-create-index``` script needs to be executed once to create the indexes required for elastalert to maintain inforamtion about rules/alerts.

```docker run -v /<rules-and-config-dir-on-source>:/<mount-dir-on-container> -i elastalert:1.0 <arguments for elastalert>```

e.g. ```docker run -v /home/elastalert-code:/app/elastalert -i elastalert:1.0 --config config/config.yaml --rule rules/example-test.yaml --verbose```


