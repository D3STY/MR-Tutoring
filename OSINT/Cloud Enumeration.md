- Finding org assets in the cloud can be a daunting task. 

- SSL Certificate Enumeration
	- SSL certificates often have other domains on them as Subject Alternative Names (SANs); these may be other external apex domains, subdomains, or even internal domains
	- [kaeferjaeger.gay](https://kaeferjaeger.gay)
		- Hacker collective that scans all major cloud providers every month and catalogues the SSL certificate information into a downloadable database
		- https://kaeferjaeger.gay/?dir=sni-ip-ranges
		- This data is not formatted; some BASH is needed:
			- `cat *.txt | grep -F ".<target_domain>" | awk -F'-- ' '{print $2}'| tr ' ' '\n' | tr '[' ' ‘| sed 's/ //’| sed 's/\]//’| grep -F ".<target_domain>“ | sort -u`

- S3 Buckets
	- https://buckets.grayhatwarfare.com/
		- Paid, but limited free results
	- Loop though subdomains looking for s3 buckets
		- `while read p; do echo $p, $(curl --silent -I -i https://$p | grep AmazonS3); done`
	- You'll need the bucket name (not just the URL) to interact with buckets using AWS CLI; you can get them from the CNAME records of the bucket URLs.
	- AWS CLI
		- `aws s3api list-objects-v2 --bucket <bucket_name> > list_objects.txt`
		- Get a total number of objects:
			- `grep '"Key"' list_objects.txt |wc -l`
		- List filenames:
			- `grep '"Key"' list_objects | sed 's/[",]//g' > list_keys.txt`
		- Search for certain file types:
			1. `patterns='\.sh$|\.sql$|\.tar\.gz$\.properties$|\.config$|\.tgz$'`
			2. `egrep $patterns list_keys.txt`
			3. `egrep -v\ "\.jpg|\.png|\.js|\.woff|/\",$|\.css|\.gif|\.svg|\.ttf|\.eot" list_keys.xt`
		- Download object by key
			- `aws s3api get-object --bucket <bucket_name> --key <key> <output_filename>`

- Resources
	- http://flaws.cloud/  
	- http://flaws2.cloud/  
	- https://google.github.io/kctf/