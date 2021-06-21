# Install Drupal 9 Locally with Lando

_Created by [David Needham](https://www.davidneedham.me/). This material was last tested on 2021/06/19._

[Play Introduction Video](https://www.youtube.com/watch?v=qs0WG2GpRwA)

Most new development projects begin on your computer. If you're comfortable in a terminal window, [Lando](https://lando.dev/) is a tool that makes it fast and for you and your colleagues to spin up customized environments. Configuration is saved and distributed with the code for your project, so each person's environments are consistent.

## Lesson 1

In this lesson, you'll learn how to use Lando to get Drupal 9 up and running on your computer in 12-minutes or less.

1. Install Lando.
    
    Lando runs on macOS, Windows, and Linux. You can find instructions and system requirements at [https://docs.lando.dev/basics/installation.html](https://docs.lando.dev/basics/installation.html). 
    
    > _Note: Lando will automatically install Docker if you do not already have it. **If you already have Docker installed, this may break your existing configuration.**_
 
 2. Open your terminal and verify that Lando installed successfully: 
    
    `lando version`

 3. Create a new folder for this project and navigate into it:

    `mkdir drupal9 && cd drupal9`

4. Lando has a helpful multistep interface for initializing a new project based on predefined recipes. We're going to streamline the process by providing all of the details in a single command. 

    Copy this entire block and run it in your terminal:
    
```
lando init \
--source remote \
--remote-url https://www.drupal.org/download-latest/tar.gz \
--remote-options="--strip-components 1" \
--recipe drupal9 \
--webroot . \
--name drupal9
```

This command will download and extract your Drupal codebase and create a `lando.yml` file for saving the configuration for this project. We don't need this right now, but you'll need it for the next lesson.

> _Note: if you already have code from an existing codebase, you may want to step through the initialization yourself with `lando init`._

5. Start the Lando containers and spin up your new environment with `lando start`.

    This step could take a minute while Lando interfaces with Docker to spin up and configure the containers for you.

    > _Fun fact: if you clone a project locally and discover a lando.yml file, you can skip the initialization and simply `lando start`. This generates an identical environment to everyone else on the project!_

6. Open the website in your browser. If you followed these steps exactly, it should be [https://drupal9.lndo.site/](https://drupal9.lndo.site/).

    Chrome will warn you that "Your connection is not private," but we expect that. We will fix this in a later lesson. 
    
    For now, let's proceed forward:

    1. Click the __Advanced__ button.
    2. Click the __Proceed to drupal9.lndo.site (unsafe)__ link.

7. All that's left is installing Drupal!
    1. Click the __Save and continue__ button.
    
    2. Choose the installation profile you want for this project. We're going to use __Demo: Umami Food Magazine (Experimental)__ to give us a prebuilt example with which to work.

    3. Click the __Save and continue__ button.
 
    4. Enter Lando's default database values for this recipe:
        1. __Database name:__ `drupal9`
        2. __Database username:__ `drupal9`
        3. __Database password:__ `drupal9`
        4. Expand the __Advanced Options__
        5. __Host:__ `database`
    
    5. Click the __Save and continue__ button.

    6. Enter a __Site email address__, __Username__, and __Password__ that you will remember.

    7. Uncheck the box __Receive email notifications__.

    8. Click the __Save and continue__ button.

__🎉 Congratulations, you have completed Lesson 1! 🎉__

### Self Evaluation

Have you mastered this lesson? Take a moment to see what you've learned.

1. What software does Lando interact with to create containers?

    a) Kubernetes

    b) Singularity

    c) Docker

    d) Vagrant

2. Open your new Drupal 9 website. What is the title of the featured recipe on the Recipes page?
    
    a) Vegan chocolate and nut brownies
    
    b) Gluten Free Pizza

    c) Fiery chili sauce

    d) Super easy vegetarian pasta bake

3. What is the command to initialize a new Lando project?

    a) lando start

    b) lando init

    c) lando initialize

    d) lando project:create

4. Lando is supported on macOS, Windows, Linux, and Android.

    a) True

    b) False

__Answers:__ ~~1c 2a 3b 4b~~

## Conclusion

Now that you have a working Drupal 9 website, you can go any direction you want. Lando is perfect for this job because you have near infinite flexibility and power of your space (without having to master Docker).

### Keep learning in the next lesson:  
 - How to customize your preferences such as the version of PHP, enable xdebug, etc.
 - How to extend the standard Drupal 9 recipe to include mail handling, solr, or node.
 - How to add essential tools such as task runners, Drush, etc.
 - How to integrate with third parties such as Pantheon's Terminus CLI or the Datadog Agent.

### Check out other courses in our Using Lando series:
 - Jump into Local WordPress Development with Lando
 - Build for Kubernetes with Lagoon and Lando
 - Create the perfect MEAN stack for JavaScript with Lando