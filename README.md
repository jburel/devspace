
Getting started
---------------

 *  Clone devspave to a directory with a meaningful name, since this will be
    part of your docker container names:

        git clone git://github.com/openmicroscopy/devspace MYTOPIC

 *  Run rename.py to match your topic name. If you do not yet have
    topic branches available on origin, use "develop" or one of the
    main branches.

        ./rename.py MYTOPIC

 *  Optionally, commit those changes to a new branch:

        git checkout -b MYTOPIC && git commit -a -m "Start MYTOPIC branch"

 * Configure the .ssh and .gitconfig files in the slave directory, e.g.:

        cp ~/.gitconfig slave/
        cp ~/.ssh/id_rsa slave/.ssh
        cp ~/.ssh/id_rsa.pub slave/.ssh

 * **If not using docker-machine**, you will need to fix the user ID
    for jenkins and slave!

 *  Start up the jenkins slave (which starts up all requirements)::

        ./ds up      # Ctrl-C to stop or
        ./ds up -d   # To disconnect

 * Check that the containers are running:

        docker ps

 *  Configure artifactory:
    - Add an artifactory user (optional)
    - Under "System Configuration" add your artifactory URL
