
# tkrn's archive control tool

In summary this is a bash command line tool to help assist posting workflows to [Browstertrix Cloud](https://github.com/webrecorder/browsertrix-cloud/) instances through their API. This tool allows you to have multiple json files that you based off the site you're looking to crawl giving you a 'template' of exclusions, tags and other parameters for your crawling needs. Additionally, you can bulk add sites by specifying a text file which is line delimited. 

![tkrnctl animation](https://github.com/tkrn/tkrnctl/blob/main/.github/tkrnctl-animation.gif?raw=true)

## tkrnctl.env

There are variables that need to be defined before using the script. BTRIX_USER and BTRIX_PASS are the credentials you use to log into Browsertrix Cloud. Additionally, you need the internal ID for the organization to submit the workflows to. That ID can be found here:

![Browsertrix Cloud Organization ID](https://github.com/tkrn/tkrnctl/blob/main/.github/tkrnctl-org-id.png?raw=true)

Install the Python3 Prerequisites:

Additional modules are required for the script to work. tkrnctl depends on `requests`, `termcolor` and `dotenv` Python modules. These can be install via `pip` 

```shell
pip install requests termcolor dotenv
```

or if installing via Ubuntu/Debian apt:

```shell
sudo apt install python3 python3-requests python3-termcolor python3-dotenv
```

Copy the example environment file for your modification:

```shell
cp tkrnctl.env.example tkrnctl.env
```

Then the following needs to be specified in tkrnctl.env:

```shell
BTRIX_USER=""  
BTRIX_PASS=""  
BTRIX_ORG=""
```

Lastly, specificy where you're warcs/wacz are located. The script will loop through the prefix of crawls to determine a list of crawled workflows/jobs.
```shell
WARCS_PATH=/dpool/arc/pywb/webarchive/collections/stacks/archive/
```

### Notice
This script was designed for internal use and use cases. It may not fit what you need to do but I'm always open to suggestions. This helps fill a gap in tool set for how I crawl for tkrn's archive. Lastly, this was developed against self-hosted solution and not Browsertrix Hosted although it should work in theory it hasn't been tested.
