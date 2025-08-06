# DISCLAIMER

This script is provided "as is" without any warranties or guarantees of any kind. 
By using this script, you acknowledge that you are solely responsible for any consequences, 
damages, or issues that may arise from its usage.

The author(s) of this script assume no responsibility or liability for any loss of data, 
system failure, downtime, security breaches, or other consequences that may result 
from running this script. Use this script at your own risk.

You should thoroughly test this script in a safe, non-production environment before using it in any live systems.

Make sure to regularly check your Digitalocean account for droplets that you do not want to run anymore
to avoid unexpected costs.

---

## hyperscale-node-stats-proxy

This cloud-init config sets up a proxy specifically configured to circumvent the CORS issue of https://github.com/prookie-radix/hyperscale-digitalocean-webui. It essentially makes the API of Radix Hyperscale nodes accessible via HTTPS.

To avoid abuse, it is whitelisted down to IPs as hosts and also to a few specific API paths, currently:

- `/api/node`
- `/api/network/statistics`
- `/api/ledger/statistics`

The target hosts IP needs to be passed as query parameter `target`.

### Example

https://proxy-host.tld/api/ledger/statistics?target=188.166.78.200

is proxied to

http://188.166.78.200:8080/api/ledger/statistics

## Compatibility

> [!IMPORTANT]
> Only tested with Ubuntu 24.04 LTS so far.
