# API for Asset Service

Assets may be retrieved using a combination of query parameters. This endpoint returns asset-type neutral summary information and supports pagination by default.

To get eligible web application assets for a target:

```bash
curl -v -H "Authorization: Bearer token" "https://platform.synack.com/api/asset/v2/assets?listingUid[]=24ehvtagyy&organizationUid[]=weultjstoe&assetType[]=webapp&active=true&scope[]=in&scope[]=discovered&sort=location&sortDir=asc&page=1&perPage=500" |jq
```

To get eligible IP host assets (of ip and cidr types) for a target:

```bash
curl -v -H "Authorization: Bearer token" "https://platform.synack.com/api/asset/v2/assets?listingUid[]=24ehvtagyy&organizationUid[]=weultjstoe&assetType[]=host&hostType[]=cidr&hostType[]=ip&active=true&scope[]=in&scope[]=discovered&sort=location&sortDir=asc&page=1&perPage=500" |jq
```


### Retrieving Synack Bearer Token
<details>
 <summary> Browser Bookmarks For Easy Retrieval </summary>
After authentication to the platform the Bearer Token for the API calls can be found in your browser session storage under shared-session-com.synack.accessToken.  On re-authenticating to the platform you will need to get this value again. Below are some bookmarks that can be used to access the token easier. 


### SynackTokenToClipBoard 
This will copy your Synack Token to the clipboard 
```
javascript:(function(){var token=sessionStorage.getItem('shared-session-com.synack.accessToken');if(!token){console.error('Token not found in session storage.');return;}var textarea=document.createElement('textarea');textarea.value=token;document.body.appendChild(textarea);textarea.select();document.execCommand('copy');document.body.removeChild(textarea);alert('Token copied to clipboard');})();
```

### Save your Synack Token to a File 
This will download the token to your default download location as synacktoken.txt   
```
javascript:(function(){var token=sessionStorage.getItem('shared-session-com.synack.accessToken');if(!token){console.error('Token not found in session storage.');return;}var blob=new Blob([token],{type:'text/plain'});var url=URL.createObjectURL(blob);var a=document.createElement('a');a.href=url;a.download='synacktoken.txt';document.body.appendChild(a);a.click();document.body.removeChild(a);URL.revokeObjectURL(url);})();
```
</details>