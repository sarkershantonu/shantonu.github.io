---
layout: post
title: How to use wget in cli?
date: "2018-03-25 05:02"
tags: [tools,linux]
permalink: /2018/03/25/wget-basics/
gh-repo: sarkershantonu/sarkershantonu.github.io
excerpt: "Blog on Tools"
gh-badge: [star,follow]
comments: true
---
In this article we are going to see how we can use wget.

### What is wget? 
Wget stands for Web Get. Wget is a CLI utilities for  HTTP, HTTPS, FTP and FTPS request in commandline . It is one of the most popular ubuntu tools used for data crawling/testing.  

### Why wget?
- Ready to run without install in ubuntu systems
- fast & easy
- site crawling is easy
- you can create batch crawler with wget.  

### Installation 
- Install via APT

         sudo apt-get update && sudo apt-get install wget       	

### Useful Options
- no Certificate checks 
           
           --no-check-certificate
- Turn Off following robot text 
      
      -e robots=off
- Level to download 
	
		-l,  --level=NUMBER       maximum recursion depth (inf or 0 for infinite).
- Accepted Patterns

		-A,  --accept=LIST               comma-separated list of accepted extensions.

### Examples 
- To download whole site (http, not https)

		 wget -r --no-parent _site_url
- Get all Ubuntu ISO files from CDN (will be hundreds of GB)

		 wget -r -l4 -A.iso http://cdimage.ubuntu.com
		
### [Official Manual](https://www.gnu.org/software/wget/manual/wget.html)

### More Options 
There are more CLI options, here is the whole list. 
		
 	Startup:
	  -V,  --version           display the version of Wget and exit.
	  -h,  --help              print this help.
	  -b,  --background        go to background after startup.
	  -e,  --execute=COMMAND   execute a `.wgetrc'-style command.

	Logging and input file:
	  -o,  --output-file=FILE    log messages to FILE.
	  -a,  --append-output=FILE  append messages to FILE.
	  -d,  --debug               print lots of debugging information.
	  -q,  --quiet               quiet (no output).
	  -v,  --verbose             be verbose (this is the default).
	  -nv, --no-verbose          turn off verboseness, without being quiet.
		   --report-speed=TYPE   Output bandwidth as TYPE.  TYPE can be bits.
	  -i,  --input-file=FILE     download URLs found in local or external FILE.
	  -F,  --force-html          treat input file as HTML.
	  -B,  --base=URL            resolves HTML input-file links (-i -F)
								 relative to URL.
		   --config=FILE         Specify config file to use.

	Download:
	  -t,  --tries=NUMBER            set number of retries to NUMBER (0 unlimits).
		   --retry-connrefused       retry even if connection is refused.
	  -O,  --output-document=FILE    write documents to FILE.
	  -nc, --no-clobber              skip downloads that would download to
									 existing files (overwriting them).
	  -c,  --continue                resume getting a partially-downloaded file.
		   --progress=TYPE           select progress gauge type.
	  -N,  --timestamping            don't re-retrieve files unless newer than
									 local.
	  --no-use-server-timestamps     don't set the local file's timestamp by
									 the one on the server.
	  -S,  --server-response         print server response.
		   --spider                  don't download anything.
	  -T,  --timeout=SECONDS         set all timeout values to SECONDS.
		   --dns-timeout=SECS        set the DNS lookup timeout to SECS.
		   --connect-timeout=SECS    set the connect timeout to SECS.
		   --read-timeout=SECS       set the read timeout to SECS.
	  -w,  --wait=SECONDS            wait SECONDS between retrievals.
		   --waitretry=SECONDS       wait 1..SECONDS between retries of a retrieval.
		   --random-wait             wait from 0.5*WAIT...1.5*WAIT secs between retrievals.
		   --no-proxy                explicitly turn off proxy.
	  -Q,  --quota=NUMBER            set retrieval quota to NUMBER.
		   --bind-address=ADDRESS    bind to ADDRESS (hostname or IP) on local host.
		   --limit-rate=RATE         limit download rate to RATE.
		   --no-dns-cache            disable caching DNS lookups.
		   --restrict-file-names=OS  restrict chars in file names to ones OS allows.
		   --ignore-case             ignore case when matching files/directories.
	  -4,  --inet4-only              connect only to IPv4 addresses.
	  -6,  --inet6-only              connect only to IPv6 addresses.
		   --prefer-family=FAMILY    connect first to addresses of specified family,
									 one of IPv6, IPv4, or none.
		   --user=USER               set both ftp and http user to USER.
		   --password=PASS           set both ftp and http password to PASS.
		   --ask-password            prompt for passwords.
		   --no-iri                  turn off IRI support.
		   --local-encoding=ENC      use ENC as the local encoding for IRIs.
		   --remote-encoding=ENC     use ENC as the default remote encoding.
		   --unlink                  remove file before clobber.

	Directories:
	  -nd, --no-directories           don't create directories.
	  -x,  --force-directories        force creation of directories.
	  -nH, --no-host-directories      don't create host directories.
		   --protocol-directories     use protocol name in directories.
	  -P,  --directory-prefix=PREFIX  save files to PREFIX/...
		   --cut-dirs=NUMBER          ignore NUMBER remote directory components.

	HTTP options:
		   --http-user=USER        set http user to USER.
		   --http-password=PASS    set http password to PASS.
		   --no-cache              disallow server-cached data.
		   --default-page=NAME     Change the default page name (normally
								   this is `index.html'.).
	  -E,  --adjust-extension      save HTML/CSS documents with proper extensions.
		   --ignore-length         ignore `Content-Length' header field.
		   --header=STRING         insert STRING among the headers.
		   --max-redirect          maximum redirections allowed per page.
		   --proxy-user=USER       set USER as proxy username.
		   --proxy-password=PASS   set PASS as proxy password.
		   --referer=URL           include `Referer: URL' header in HTTP request.
		   --save-headers          save the HTTP headers to file.
	  -U,  --user-agent=AGENT      identify as AGENT instead of Wget/VERSION.
		   --no-http-keep-alive    disable HTTP keep-alive (persistent connections).
		   --no-cookies            don't use cookies.
		   --load-cookies=FILE     load cookies from FILE before session.
		   --save-cookies=FILE     save cookies to FILE after session.
		   --keep-session-cookies  load and save session (non-permanent) cookies.
		   --post-data=STRING      use the POST method; send STRING as the data.
		   --post-file=FILE        use the POST method; send contents of FILE.
		   --content-disposition   honor the Content-Disposition header when
								   choosing local file names (EXPERIMENTAL).
		   --content-on-error      output the received content on server errors.
		   --auth-no-challenge     send Basic HTTP authentication information
								   without first waiting for the server's
								   challenge.

	HTTPS (SSL/TLS) options:
		   --secure-protocol=PR     choose secure protocol, one of auto, SSLv2,
									SSLv3, and TLSv1.
		   --no-check-certificate   don't validate the server's certificate.
		   --certificate=FILE       client certificate file.
		   --certificate-type=TYPE  client certificate type, PEM or DER.
		   --private-key=FILE       private key file.
		   --private-key-type=TYPE  private key type, PEM or DER.
		   --ca-certificate=FILE    file with the bundle of CA's.
		   --ca-directory=DIR       directory where hash list of CA's is stored.
		   --random-file=FILE       file with random data for seeding the SSL PRNG.
		   --egd-file=FILE          file naming the EGD socket with random data.

	FTP options:
		   --ftp-user=USER         set ftp user to USER.
		   --ftp-password=PASS     set ftp password to PASS.
		   --no-remove-listing     don't remove `.listing' files.
		   --no-glob               turn off FTP file name globbing.
		   --no-passive-ftp        disable the "passive" transfer mode.
		   --preserve-permissions  preserve remote file permissions.
		   --retr-symlinks         when recursing, get linked-to files (not dir).

	WARC options:
		   --warc-file=FILENAME      save request/response data to a .warc.gz file.
		   --warc-header=STRING      insert STRING into the warcinfo record.
		   --warc-max-size=NUMBER    set maximum size of WARC files to NUMBER.
		   --warc-cdx                write CDX index files.
		   --warc-dedup=FILENAME     do not store records listed in this CDX file.
		   --no-warc-compression     do not compress WARC files with GZIP.
		   --no-warc-digests         do not calculate SHA1 digests.
		   --no-warc-keep-log        do not store the log file in a WARC record.
		   --warc-tempdir=DIRECTORY  location for temporary files created by the
									 WARC writer.

	Recursive download:
	  -r,  --recursive          specify recursive download.
	  -l,  --level=NUMBER       maximum recursion depth (inf or 0 for infinite).
		   --delete-after       delete files locally after downloading them.
	  -k,  --convert-links      make links in downloaded HTML or CSS point to
								local files.
	  -K,  --backup-converted   before converting file X, back up as X.orig.
	  -m,  --mirror             shortcut for -N -r -l inf --no-remove-listing.
	  -p,  --page-requisites    get all images, etc. needed to display HTML page.
		   --strict-comments    turn on strict (SGML) handling of HTML comments.

	Recursive accept/reject:
	  -A,  --accept=LIST               comma-separated list of accepted extensions.
	  -R,  --reject=LIST               comma-separated list of rejected extensions.
		   --accept-regex=REGEX        regex matching accepted URLs.
		   --reject-regex=REGEX        regex matching rejected URLs.
		   --regex-type=TYPE           regex type (posix).
	  -D,  --domains=LIST              comma-separated list of accepted domains.
		   --exclude-domains=LIST      comma-separated list of rejected domains.
		   --follow-ftp                follow FTP links from HTML documents.
		   --follow-tags=LIST          comma-separated list of followed HTML tags.
		   --ignore-tags=LIST          comma-separated list of ignored HTML tags.
	  -H,  --span-hosts                go to foreign hosts when recursive.
	  -L,  --relative                  follow relative links only.
	  -I,  --include-directories=LIST  list of allowed directories.
	  --trust-server-names             use the name specified by the redirection
									   url last component.
	  -X,  --exclude-directories=LIST  list of excluded directories.
	  -np, --no-parent                 don't ascend to the parent directory.
