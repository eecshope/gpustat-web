gpustat-web
===========

A web interface of [`gpustat`][gpustat] ---
aggregate `gpustat` across multiple nodes forked and modified from @wookayin.

<p align="center">
  <img src="screenshot.png" width="800" height="192" />
</p>

**UPDATE**: This version allows you to set the exec path of `gpustat` manually and separately for each node with a JSON config file.

**NOTE**: This project is in alpha stage. Errors and exceptions are not well handled, and it might use much network resources. Please use at your own risk!


Usage
-----

Launch the application as follows. SSH connections will be established to each of the specified hosts.
Make sure ssh works under a proper authentication scheme such as SSH key (e.g. `id-rsa`).
It is known that asyncssh [does NOT obey](https://github.com/ronf/asyncssh/issues/108) `~/.ssh/config` file
(e.g. alias, username, keyfile), so just be aware of this.

```
python -m gpustat_web --port 48109 --config CONFIG_PATH
```

Please use `python=3.6` only. 

The config file is JSON list. Each element in the JSON list is a small list of two element: [ADDRESS:PORT, GPUSTAT PATH]. Considering that
most of the users install `gpustat` with virtual environment, it is more convenient to specify `gpustat` path manually. 

[gpustat]: https://github.com/wookayin/gpustat/


License
-------

MIT License

Copyright (c) 2022-2022 Zejun Wang
