- Scraping
	- Tons of databases and data projects exist to catalogue related URLs and domains
	- Google Dorking
		- Google a domain, then progressively subtract known subdomains
			1. site:twitch.tv -www.twitch.tv  
			2. site:twitch.tv -www.twitch.tv -watch.twitch.tv  
			3. site:twitch.tv -www.twitch.tv -watch.twitch.tv -dev.twitch.tv
			4. ...
	- [Amass](https://github.com/caffix/amass)
		- Will automatically extract subdomain data from tons of sources and optionally brute force subdomains as well.
		- Also groups scraped domains to ASNs, owners, and IP ranges
		- Make sure to review the [API Keys](obsidian://open?vault=Necronomicon&file=Necronomicon%2FOSINT%2FAPI%20Keys) page to make your Amass as much as it can be
			- `amass enum –list`
			- `amass enum -list | grep -v "\*"`
			- Put the keys in `~/.config/amass/config.ini`
	- [Subfinder](https://github.com/subfinder)
		- Similar to Amass - use both and concat | uniq the output
	- [BBOT](https://github.com/blacklanternsecurity/bbot)
		- Huge tool with subdomain scraping, brute force, web spidering, and more.
		- The output is a file at `/root/.bbot/scans/{scan_name}/`
			- `cat /root/.bbot/scans/{scan_name}/output.txt | grep -F '[DNS_NAME]’ | awk '{print $2}'`

- Subdomain brute force
	- Very slow - try using threaded tools that will use multiple DNS resolvers
	- [PureDNS](https://github.com/d3mondev/puredns)
		- Wrapper around [MassDNS](https://github.com/blechschmidt/massdns) and adds features
		- `puredns bruteforce <subdomain_list> tesla.com -r resolvers.txt`
	- DNS resolvers: https://github.com/trickest/resolvers
	- Permutation/Alteration scanning - predict other subdomain names based on patterns
		- [altdns](https://github.com/infosec-au/altdns) - generate permutations, but doesn't attempt to resolve. Use with PureDNS
		- [dnsgen](https://github.com/ProjectAnte/dnsgen.git) - generate permutations, but doesn't attempt to resolve. Use with PureDNS
			- `cat <file_of_subdomains.txt> | dnsgen - | puredns resolve --resolvers resolvers.txt`

- Shodan
	- [Shosubgo](https://github.com/incogbyte/shosubgo)
		- `go run main.go -d <target_domain>`
	- Shodan from CLI is better for large targets - NahamSec has a great video on this and parsing output
		- [NahamSec - Asset Discovery Using Shodan](https://www.youtube.com/watch?v=4CL_8GRNVTE)
	
 - Acquisitions
	 - [Crunchbase](https://www.crunchbase.com/)
		- Business information about acquisitions and mergers - new apex domains that belong to your target for enumeration, phishing, etc.
		- Companies often don't force newly acquired companies to change to their infrastructure immediately.
		- Also gives:
			- information on company leadership and employees - even past employees
			- Tech stack info
			- Annual revenue
			- Events
			- Recent news
			- Other fantastic contextual data
	- [OCCRP](https://aleph.occrp.org)
		- global archive of research material for investigative reporting. They keep track of 414 million public entities and parse over 252 discrete datasets in more than 141 countries.
		- When searching for a company, find the entry that comes up, closely related to your company and associated with the dataset "US SEC CorpWatch.“
			- Look for one with a substantial list of assets
		- Provides a list of acquisitions and investments by your target

- Reverse WHOIS
	- The purpose of this is to search WHOIS data to hopefully find other apex domains owned by the target.
	- For example, searching WHOIS data for the "Organization Name" or "Registrant Email" of the target
	- https://whoxy.com - cheapest place for access to reverse WHOIS and WHOIS data in general.
		- API - 1000 queries for $10
			- `https://api.whoxy.com/?key=xxxxx&reverse=whois&keyword=google&mode=domains`

- Using AI for recon
	- *Current dataset cuts off in 2021; all results should be rigorously verified*
	- Acquisitions
		- "What can you tell me about Tesla's acquisitions?"
	- Subdomains
		- [SubreconGPT](https://github.com/jhaddix/SubreconGPT)
			- Script that accepts a list of subdomains and for each one, it will have GPT4 guess similar/related subdomains and check whether they resolve

- Linked Discovery
	- This essentially involves spidering pages at the known domains of the target to discover more related domains.
	- BurpSuite:
		1. Turn off passive scanning
		2. Set forms auto to submit (if you’re feeling frisky)  
		3. Set scope to advanced control and use “keyword” of target name (not a normal FQDN)  
		4. Walk+browse main site, then spider all hosts recursively!  
		5. Profit
		- To export the found domains/subdomains:
			1. Select all hosts in the site tree  
			2. In PRO ONLY right click the selected hosts
			3. Go to “Engagement Tools” -> “Analyze target”
			4. Save report as an html file  
			5. Copy the hosts from the “Target” section
	- [GoSpider](https://github.com/jaeles-project/gospider)
	- [hakrawler](https://github.com/hakluke/hakrawler)

- Ad & Analytics
	- You can also glean related domains and subdomains by looking at a target’s ad/analytics tracker codes. Many sites use the same codes across all their domains. Google analytics and New Relic codes are the most common.
	- [BuiltWith](https://builtwith.com/)
		- Example: https://builtwith.com/relationships/twitch.tv
		- [getrelationship.py](https://raw.githubusercontent.com/ m4ll0k/Bug-Bounty- Toolz/master/getrelationship.py)
			- Will search BuiltWith from the command line with the help of your session token.

- Discover cloud endpoints behind Cloudflare, Akamai, etc.
	- Pull CNAME records from domains
		- `getent hosts <domain>`
	- Analyze public IPs and cross-reference with IP ranges of various services like AWS
		- [DNSCharts](https://dnscharts.hacklikeapornstar.com/)
	- 