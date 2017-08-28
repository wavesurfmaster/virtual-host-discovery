# Virtual host scanner
This is a basic HTTP scanner that'll enumerate virtual hosts on a given IP address. During recon, this might help expand the target by detecting old or deprecated code. It may also reveal hidden hosts that are statically mapped in the developer's `/etc/hosts` file.

## Usage
The tool comes with a few basic options. They are listed below and help narrow down virtual hosts.

```
ruby scan.rb --ip=192.168.1.101 --host=domain.tld
```

Here's a list of all available options:

 - **--ignore-http-codes**: a comma-separated list of HTTP status codes to be ignored in the scan results. This may become useful when the scan results are poluted with false-positives that are identified by their HTTP response code.
 - **--ignore-content-length**: a content length filter which should be ignored in the scan results. This may become useful when a server returns a static page on every virtual host guess.
 - **--port**: when the web server isn't running on port 80.