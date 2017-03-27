# Raspberry Pi Camera Monitor/Alert
Takes photo from Raspberry Pi and uploads to transfer.sh with optional Slack/IFTTT alert.

## Requirements

This script requires the following services/tools.
1. [transfer.sh](https://transfer.sh/)
2. [Slack](https://slack.com/)
2. [IFTTT](https://ifttt.com/)

## Scripts

The reason the steps are broken into individual scripts is because the camjob will be rewritten
using `python-picamera` with the motion sensor module.

- `camjob`
    - Takes a picture using raspistill and save jpg to /tmp.
- `snitch`
    - Uploads the file to [transfer.sh](https://transfer.sh/), optionally notify Slack channel and/or IFTTT.
    - This script can be used independently as well! ( ͡° ͜ʖ ͡°)

## Setup

Most common usage is to setup a cronjob and run this at an interval.

## Encryption

If encryption is set to `true`, the file will be encrypted using `openssl`. The following command can be used to decrypt once the file is downloaded.

```
$ openssl enc -d -aes256 -salt -in <input_file> -out <output_file> -k <password>
```

# Contributors

Calvin Wong

# License

The utilities in this repo are distributed under the
[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0),
see LICENSE and NOTICE for more information.

# Repo Location

[https://gitlab.com/cwong47/picam-monitor](https://gitlab.com/cwong47/picam-monitor.git)
