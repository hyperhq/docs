## attach

    Usage: hyper fip attach [OPTIONS] FIP CONTAINER

    Attach floating IP to a (running) container

      --help=false         Print usage

Attach an allocated floating IP to a (running) container:

	$ hyper fip attach 211.98.26.102 myweb
	myweb

If you attempt to attach the floating IP to a running container, Hyper_ return an error:

	$ hyper fip attach 211.98.26.102 myweb
	myweb is not running

Each container can have only one floating IP. Trying to attach another floating IP will return an error:

	$ hyper fip attach 211.98.26.102 myweb
	myweb is associated with 211.98.26.101