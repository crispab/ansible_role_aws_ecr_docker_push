crisp.aws_ecr_docker_push
============================

*Crisp AWS Elastic Container Registry Docker Push*

This role creates a ECR and pushes a provided Docker image to the ECR.


Requirements
------------

AWS credentials. 
AWS CLI.
Permissions to create a Elastic Container Registry.
Permissions to publish to a Elastic Container Registry.

Packages:

* boto3
* docker


Role Variables
--------------

`ecr_name` - The name of the Elastic Container Reqistry to create/use.
Example value: *betrcode/goodtimes*

`region` - The AWS region to use. 
Example value: *eu-west-1*

`source_image_name` - The source image name. 
Example value: *betrcode/goodtimes*

`source_image_tag` - The source image tag.
Example value: *latest*

`destination_image_tag` - The destination image tag. 
Will default to the `source_image_tag` if not set.
Example value: *latest*

`debugging` - Set this to true (or any value) to turn on debug statements.

The output variable `full_destination_image` can be used by
later tasks, for instance to know which image to download from a userdata script
in a AWS AutoScalingGroup.


Dependencies
------------

Not dependent on any other role.


Example Playbook
----------------

---

    - hosts: localhost
      connection: local
      roles:
        - role: betrcode.aws_ecr_docker_push
          ecr_name: betrcode/goodtimes
          region: eu-west-1
          source_image_name: betrcode/goodtimes
          source_image_tag: latest


License
-------

MIT


Author Information
------------------

Max Wenzin, partner at Crisp

https://www.crisp.se/konsulter/max-wenzin

