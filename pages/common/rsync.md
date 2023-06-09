# rsync

> Transfer files either to or from a remote host (but not between two remote hosts).
> Can transfer single files or multiple files matching a pattern.
> More information: <https://manned.org/rsync>.

- Transfer a file from local to a remote host:

`rsync {{path/to/local_file}} {{remote_host}}:{{path/to/remote_directory}}`

- Transfer a file from a remote host to local:

`rsync {{remote_host}}:{{path/to/remote_file}} {{path/to/local_directory}}`

- Transfer a file in [a]rchive (to preserve attributes) and compressed ([z]ipped) mode displaying [v]erbose and [h]uman-readable [P]rogress:

`rsync -azvhP {{path/to/local_file}} {{remote_host}}:{{path/to/remote_directory}}`

- Transfer a directory and all its contents from a remote host to local:

`rsync -r {{remote_host}}:{{path/to/remote_directory}} {{path/to/local_directory}}`

- Transfer directory contents (but not the directory itself) from a remote host to local:

`rsync -r {{remote_host}}:{{path/to/remote_directory}}/ {{path/to/local_directory}}`

- Transfer a directory [r]ecursively, in [a]rchive (to preserve attributes), resolving contained sym[L]inks, and ignoring already transferred files [u]nless newer:

`rsync -rauL {{remote_host}}:{{path/to/remote_directory}} {{path/to/local_directory}}`

- Transfer a file over SSH and delete remote files that do not exist locally:

`rsync -e ssh --delete {{remote_host}}:{{path/to/remote_file}} {{path/to/local_file}}`

- Transfer a file over SSH using a different port than the default and show global progress:

`rsync -e 'ssh -p {{port}}' --info=progress2 {{remote_host}}:{{path/to/remote_file}} {{path/to/local_file}}`
