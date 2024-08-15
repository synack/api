# api-assets
API for Asset Service

Assets may be retrieved using a combination of query parameters. This endpoint returns asset-type neutral summary information and supports pagination by default.

To get eligible web application assets for a target:

```bash
curl -v -H "Authorization: Bearer token" "https://platform.synack.com/api/asset/v2/assets?listingUid[]=24ehvtagyy&organizationUid[]=weultjstoe&assetType[]=webapp&active=true&scope[]=in&scope[]=discovered&sort=location&sortDir=asc&page=1&perPage=500" |jq
```

To get eligible IP host assets (of ip and cidr types) for a target:

```bash
curl -v -H "Authorization: Bearer token" "https://platform.synack.com/api/asset/v2/assets?listingUid[]=24ehvtagyy&organizationUid[]=weultjstoe&assetType[]=host&hostType[]=cidr&hostType[]=ip&active=true&scope[]=in&scope[]=discovered&sort=location&sortDir=asc&page=1&perPage=500" |jq
```
