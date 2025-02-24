# espanso

## Overview 


<img src="doc/curl.gif" width="900">

### Setup 

<details>

<summary>Sample Code</summary>

```
matches:
  - trigger: ":curl"
    replace: "curl -svo /dev/nul -w 'http_code:%{http_code}\\ntime_namelookup:%{time_namelookup}\\ntime_connect:%{time_connect}\\ntime_appconnect:%{time_appconnect}\\ntime_pretransfer:%{time_pretransfer}\\ntime_starttransfer:%{time_starttransfer}\\ntime_total:%{time_total}\\n' https://{{form1.name}}"
    label: "curl performance"
    vars:
    - name: form1
      type: form
      params:
        layout: |
          Type in Domain [[name]]

  - trigger: ":curl"
    replace: "curl -svo /dev/nul -w 'http_code:%{http_code}\\ntime_namelookup:%{time_namelookup}\\ntime_connect:%{time_connect}\\ntime_appconnect:%{time_appconnect}\\ntime_pretransfer:%{time_pretransfer}\\ntime_starttransfer:%{time_starttransfer}\\ntime_total:%{time_total}\\n' https://{{form1.name}} --resolve '{{form1.name}}:443:{{form1.ip}}'"
    label: "curl performance with resolve"
    vars:
    - name: form1
      type: form
      params:
        layout: "Type in Domain [[name]] \nType in IP [[ip]]"
```
</details>
