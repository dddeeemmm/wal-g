wal-g
=========

    Install and configure wal-g


Role Variables
--------------

    walg_install: true                                      [ true | false ] for install wal-g
    walg_archive_command: false                             [ true | false ] for add archive_command to postgresql.conf
    walg_cronjob: false                                     [ true | false ] for create daily full backup cronjob
    walg_postgresql_version:                                [ required ] postgresql version
    walg_aws_access_key_id: ''                              [ required ] aws access key id
    walg_aws_secret_access_key: ''                          [ required ] aws secret access_key
    walg_aws_s3_prefix: "s3://my-minio-bucket/sub-dir"      [ required ] aws s3 prefix
    walg_aws_endpoint: http://minio:9000                    [ required ] aws endpoint
    walg_aws_region: ''                                     [ required ] aws region

Example Playbook
----------------

    - hosts: server
      vars:
        walg_postgresql_version: 12
        walg_aws_access_key_id: ''                              
        walg_aws_secret_access_key: ''                          
        walg_aws_s3_prefix: "s3://my-minio-bucket/sub-dir"      
        walg_aws_endpoint: http://minio:9000                    
        walg_aws_region: ''
      roles:
      - { role: wale, tags: wale }

License
-------

    MIT

Author Information
------------------

    Dmitrij Petrov
