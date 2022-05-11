## Avalanche with subnets

### DFK Support
If you have an existing avalanche node **built from source** you can use your existing node, to install please follow the process outlined in the attached dfk.pdf.

If you would like to use our docker image and sync from scratch please do the following

<ol>
  <li>Add the instance public ip to config.json</li>
  <li>Adjust config.json as needed, for example pruning can be enabled or disabled, NOTE: do not change chain-config-dir setting</li>
  <li>Set desired data volume</li>
  <li>Start the container and wait for primary network to synchronize (takes 3-5 days)</li>
  <li> Validate the subnet with the following RPC call 
  `curl -X POST --data '{
    "jsonrpc":"2.0",
    "id"     :1,
    "method" :"platform.getBlockchains",
    "params" :{}
}' -H 'content-type:application/json;' 127.0.0.1:9650/ext/P`

The subnet id should show in the response `Vn3aX6hNRstj5VHHm63TCgPNaeGnRSqCYXQqemSqDd2TQH4qJ`
  </li>
</ol>