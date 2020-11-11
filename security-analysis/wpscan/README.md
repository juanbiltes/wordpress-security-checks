# About WPScan

> WPScan is a free, for non-commercial use, black box WordPress security scanner written for security professionals and blog maintainers to test the security of their WordPress websites.

[Repository](https://github.com/wpscanteam/wpscan) with over 5k stars. Running it provides a lot of information. 

If you want, there's a paid API Token which allows you to use the DB information that the tool uses internally, more info about it [here](https://wpscan.com/profile). **The tool doesn't need this API Token to detail the information of the results**.

## Documentation
You can find the tool documentation [in its repository wiki](https://github.com/wpscanteam/wpscan/wiki/WPScan-User-Documentation)

## Installment

- Run `docker pull wpscanteam/wpscan`

### Usage
Considering your app runs on port `8000` and you have a host entry in `/etc/hosts` as `127.0.0.1 wordpress-security.com`:

0. Enter the directory of your computer where you want the results to be saved
1. Run `docker run -it --add-host=wordpress-security.com:172.18.0.1 --rm --mount type=bind,source=$PWD,target=/output wpscanteam/wpscan:latest -o /output/results_wpscan-$(date '+%F@%T').txt --url 'http://wordpress-security.com:8000' --connect-timeout 120000 --request-timeout 1200000`
2. Find the results written as `results_wpscan-<TIMESTAMP>`

Notes:
- `--add-host=wordpress-security.com:172.18.0.1`:\
Adds a host pointing to the IP addr that WordPress has inside its docker image.
  - `172.18.0.1` is the ip that your WordPress has **inside your docker** image. In case you don't know this you can find it easily by entering your docker image and checking in the logs on which ip it was initiated. Needless to mention, you can't use `localhost` since that would point to the internal docker localhost.
  - `wordpress-security.com` is a hostname we invented for this POC


- `--mount type=bind,source=$PWD,target=/output wpscanteam/wpscan:latest -o /output/results_wpscan-$(date '+%F@%T').txt`:
  - Writes the output of the tests to the local machine
- `--url 'http://wordpress-security.com:8000'`:
  - URL where you want this to run. As we mentioned previously, we invented a hostname for our app.

## Results

You can find some results in this directory of the repository. We've also added logs inside [`logs-docker-image.txt`](./logs-docker-image.txt) of what executed on our WordPress server in case that's of your interest.