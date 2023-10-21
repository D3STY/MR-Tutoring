- Most tools designed to scan Github are targetted at a single repo or organization. This is the opposite of what a red teamer wants: they want to scour *all* repos, including (especially) private repos, for information related to the target organization
- [github-subdomains](https://github.com/gwen001/github-subdomains.git)
	- Scrapes Github for any subdomains of the target. 
	- You'll need many API keys and many runs to complete this method
- Github Dorking
	- [Gdorklinks.sh](https://gist.github.com/jhaddix/1fb7ab2409ab579178d2a79959909b33#file-gdorklinks-sh)
		- Hugely useful Haddix script to auto-generate Github dorking links
		- Usage:
			1. download the script
			2. `chmod +x Gdorklinks.sh`
			3. `./Gdorklinks.sh NameOfSomeCompanyMaybe`
			4. Paste links into browser
	- Useful queries:
		- `org:<org_name> password`
		- `org:<org_name> aws_secret_access_key`
		- `org:<org_name> aws_key`
		- `org:<org_name> BEGIN RSA PRIVATE KEY`
		- `org:<org_name> BEGIN OPENSSH PRIVATE KEY`
		- `org:<org_name> secret_key`
		- `org:<org_name> hooks.slack.com/services`
		- `org:<org_name> sshpass -p`
		- `org:<org_name> sq0csp`
		- `org:<org_name> apps.googleusercontent.com`
		- `org:<org_name> extension:pem key`
- Searching Repos for Sensitive Info:
	1. Download all repos:
		- `while read p; do git clone www.github.com/<org_name>/$p; done`
	2. Use the "Useful Grep Regexes" page included in the Necronomicon to search:
		- `egrep -Ri -f regex_patterns.txt *`
	3. Search past commits:
		- `git rev-list --all | xargs git grep "BEGIN [EC|RSA|DSA|OPENSSH] PRIVATE KEY"`
		- `git rev-list --all | xargs git grep "aws_secret"`
- [github-search](https://github.com/gwen001/github-search)
- [@th3g3ntelman's "Github and Sensitive Data Exposure"](https://www.youtube.com/watch?v=l0YsEk_59fQ)
- Internal packages and libraries
	- Companies often create internal libraries and packages, some of which accidentally get published
	- Check for archival: https://www.skypack.dev/
	- List npm contributors that have access to modify a package:
		- `npm owner ls <package_name>`

```BASH
#!/bin/bash
without_suffix=`echo $1|cut -d . -f1`
echo ""
echo "************ Github Dork Links (must be logged in) *******************"
echo "  password"
echo "https://github.com/search?q=%22$1%22+password&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+password&type=Code"
echo " npmrc _auth"
echo "https://github.com/search?q=%22$1%22+npmrc%20_auth&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+npmrc%20_auth&type=Code"
echo " dockercfg"
echo "https://github.com/search?q=%22$1%22+dockercfg&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+dockercfg&type=Code"
echo "  pem private"
echo "https://github.com/search?q=%22$1%22+pem%20private&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+extension:pem%20private&type=Code"
echo "  id_rsa"
echo "https://github.com/search?q=%22$1%22+id_rsa&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+id_rsa&type=Code"
echo " aws_access_key_id"
echo "https://github.com/search?q=%22$1%22+aws_access_key_id&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+aws_access_key_id&type=Code"
echo "  s3cfg"
echo "https://github.com/search?q=%22$1%22+s3cfg&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+s3cfg&type=Code"
echo " htpasswd"
echo "https://github.com/search?q=%22$1%22+htpasswd&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+htpasswd&type=Code"
echo " git-credentials"
echo "https://github.com/search?q=%22$1%22+git-credentials&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+git-credentials&type=Code"
echo " bashrc password"
echo "https://github.com/search?q=%22$1%22+bashrc%20password&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+bashrc%20password&type=Code"
echo " sshd_config"
echo "https://github.com/search?q=%22$1%22+sshd_config&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+sshd_config&type=Code"
echo " xoxp OR xoxb OR xoxa"
echo "https://github.com/search?q=%22$1%22+xoxp%20OR%20xoxb%20OR%20xoxa&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+xoxp%20OR%20xoxb&type=Code"
echo "  SECRET_KEY"
echo "https://github.com/search?q=%22$1%22+SECRET_KEY&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+SECRET_KEY&type=Code"
echo " client_secret"
echo "https://github.com/search?q=%22$1%22+client_secret&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+client_secret&type=Code"
echo " sshd_config"
echo "https://github.com/search?q=%22$1%22+sshd_config&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+sshd_config&type=Code"
echo " github_token"
echo "https://github.com/search?q=%22$1%22+github_token&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+github_token&type=Code"
echo "  api_key"
echo "https://github.com/search?q=%22$1%22+api_key&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+api_key&type=Code"
echo " FTP"
echo "https://github.com/search?q=%22$1%22+FTP&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+FTP&type=Code"
echo " app_secret"
echo "https://github.com/search?q=%22$1%22+app_secret&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+app_secret&type=Code"
echo "  passwd"
echo "https://github.com/search?q=%22$1%22+passwd&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+passwd&type=Code"
echo " s3.yml"
echo "https://github.com/search?q=%22$1%22+.env&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+.env&type=Code"
echo " .exs"
echo "https://github.com/search?q=%22$1%22+.exs&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+.exs&type=Code"
echo " beanstalkd.yml"
echo "https://github.com/search?q=%22$1%22+beanstalkd.yml&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+beanstalkd.yml&type=Code"
echo " deploy.rake"
echo "https://github.com/search?q=%22$1%22+deploy.rake&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+deploy.rake&type=Code"
echo " mysql"
echo "https://github.com/search?q=%22$1%22+mysql&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+mysql&type=Code"
echo " credentials"
echo "https://github.com/search?q=%22$1%22+credentials&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+credentials&type=Code"
echo "  PWD"
echo "https://github.com/search?q=%22$1%22+PWD&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+PWD&type=Code"
echo " deploy.rake"
echo "https://github.com/search?q=%22$1%22+deploy.rake&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+deploy.rake&type=Code"
echo " .bash_history"
echo "https://github.com/search?q=%22$1%22+.bash_history&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+.bash_history&type=Code"
echo " .sls"
echo "https://github.com/search?q=%22$1%22+.sls&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+PWD&type=Code"
echo " secrets"
echo "https://github.com/search?q=%22$1%22+secrets&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+secrets&type=Code"
echo " composer.json"
echo "https://github.com/search?q=%22$1%22+composer.json&type=Code"
echo "https://github.com/search?q=%22$without_suffix%22+composer.json&type=Code"
```