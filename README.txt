After provisioning master and slave:
-----------------------------------------
-manually copy the master pub ssh key to the slave's authorized_keys

Further Jenkins master setup:
----
-gain access via the default admin pwd; finish setup with default plugins
-create your admin user
-switch to matrix security
-give admin user all rights in the matrix
-add a restricted dev user
-give this restricted user the following permissions:
    OVERALL: read
    CREDENTIALS: NONE
    AGENT: NONE
    JOB: build,cancel,configure,discover,read, workspace (maybe give create...)
    RUN: update
    VIEW: configure, create, read 
    SCM: NONE
-PLUGINS:
    -Amazon EC2 plugin