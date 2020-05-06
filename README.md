# docker-jenkins-homework

hw-job1:
In this job I copied the github repo URL with dev1 branch . Then I copied the downloaded files from jenkins workspace to /test and mapped 
/test to /usr/local/apache2/htdocs/ in the testing docker environment
        sudo docker run -dit --name testweb -p 8081:80 -v /test:/usr/local/apache2/htdocs/ httpd

hw-job2:
In this job I copied the github repo URL with master branch . Then I copied the downloaded files from jenkins workspace to /production and mapped /production to /usr/local/apache2/htdocs/ in the production docker environment
        sudo docker run -dit --name production -v /production:/usr/local/apache2/htdocs/ -p 8082:80 httpd

hw-job3:
In this job I added github repo url and added credential(github username and password) that's all. Then specified branch as dev branch. QUA Team can either manually build or write script. Now got to Post-build Actions. Here Git publisher will auto merge git branches upon build. Make this configuration and you are done. And remove the dev-docker (test) container once QUA Team approves the feature.

