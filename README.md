# Cloudflare DDNS Updater

A Dynamic DNS client (bash script) for a Cloudflare hosted domain.

Whenever your public IP changes, run the script. It will work out what your current IP is and poke it into your nominated DNS record!

## Usage

```
$ ./ddns
```

## Setup

Ensure `jq` is installed, then edit the ddns script, setting the following:
* Set `email` to the email associated with your Cloudflare account,
* Set `token` to a Cloudflare API Key with permissions to edit your DNS zone,
* Set `domain` to your Cloudflare-managed domain name (ie: `example.com`),
* Set `record` to the name of the "A"-type record you want to keep updated (ie: `acme.example.com`).

If needed, set the execute bit on the script (`chmod +x ddns`).

To create a Cloudflare API Key, log into your Cloudflare account then click through to your Profile, then API Tokens. 
* Click `Create Token` then `Use Template` next to `Edit zone DNS`.  
* Under permissions, select `Zone`, `DNS` and `Edit`.  
* Under Zone Resources, select `Include`, `Specific zone`, and your domain (`example.com`).  
* Specify a TTL if desired, then save and record the resulting key.
