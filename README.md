# Superfund Remediation
Notes for a talk about best practices around containerizing python applications

Title:
------
Cleaning Up Your Python Environment Superfund Site (with containers)

Conference:
-----------
PyColorado 2019
Sunday, 9/8 : 9:30am - 10:10am
Denver, CO

Talk Format:
------------
Talk - 30 minutes

Description:
------------
Does your python environment look like randall munroe’s (of XKCD fame) python environment superfund site? (https://xkcd.com/1987/) What would happen to your sprint if your laptop got hit by a bus? How can you mitigate that? Learn how to make your application's environmental dependencies reproducible.


Who and Why (Audience):
-----------------------
This presentation will go over how to use venv, pipenv, docker and docker-compose to safely and reproducible wrap a small application in a docker container, and place other services in there with it so that you can move local dependencies out of the README (install postgresql version 8.1) and into a codified reproducible, ephemeral (start up from scratch and tear it down in seconds)

This allows for 1. Faster on-boarding (just install docker and go!) 2. Makes testing edge cases easier (how does your application behave when the database host goes away) 3. Allows you to save the build arguments in a readable manner 4. Consistent environments across the entire team


Outline:
--------

* INTRODUCTION AND OUTLINE                      (x minutes, x total)
    - Quick introduction of myself
    - Outline of what will be covered and what you will learn
    - My motivation for giving this talk
* WHY?                                          (x minute, x total)
    - Why should you care about containerizing?
    - This is not python specific, these strategies are universally applicable!
* OVERVIEW                                      (x minutes, x total)
    - Package managers (whichever)
    - Docker
    - Docker Compose
* APP                                           (x minutes, x total)
    - Write a raw script that subscribes to a websocket
        * the application requires python3 to be installed
        * introduce pip versioning conflict
        * resolve with pipenv
        * the application requires pipenv to be installed
    - Now the README has some important step that are required
        * Code is better than documentation
        * Specify python and pipenv install in Dockerfile
    - Introduce functionality that saves to mongoDB
        * You're planning on using DocumentDB
        * MongoDB 3.6 is required, but you have 4.2 installed for another project
        * Write a docker-compose file that contains both services
* REPRODUCIBILITY
    - The environment is more stable now
    - Onboarding is easier
    - Integration testing is easier
    - Unit testing is easier
    - Linting is easier
* STRETCH GOALS
    - the application waits for the database to come up
    - unit or integration testing service in the docker-compose
    - docker networking, what’s the difference between expose, ports and host networking


Bio:
----
Ashton Honnecke is a software engineer with [Digital Assets Data](https://www.digitalassetsdata.com/), a fintech and data company building enterprise-grade software and data feeds for crypto hedge funds and other market participants.

