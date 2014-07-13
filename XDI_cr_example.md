Respect Network XDI Consent Receipt
Data Subject: Alice  [=]!:uuid:1111
Data Controller: Amazon  [+]!:uuid:9999
Third Parties: UPS  [+]!:uuid:8888
In Alice's and Amazon's cloud:
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#location><$uri>&/&/"....."
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#location><#digital>&/&/true
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#explicit>&/&/true
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#purpose>&/&/"...."
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<$t>&/&/"2014-07-13T21:32:52"
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#privacy><#policy><$uri>&/&/"https://..."
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#cookie><#policy><$uri>&/&/"https://..."
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#tos><$uri>&/&/"https://..."
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#short><#privacy><#notice><$uri>&/&/"https://..."
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#dnt>&/&/true
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#sensitive>&/&/true
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234<#jurisdiction>/$ref/[=]!:uuid:1111<#jurisdiction>
[=]!:uuid:1111<#jurisdiction>&/&/"USA"
[+]!:uuid:9999<#jurisdiction>&/&/"DE"
In Amazon's clouds:
([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234  <-- copy of the receipt
[=]!:uuid:1111<#email>&/&/"alice@gmail.com"
[=]!:uuid:1111#address<#street>&/&/"Street 123"
[=]!:uuid:1111#address<#country>&/&/"DE"
[=]!:uuid:1111#address<#postal><#code>&/&/"23544"
([+]!:uuid:9999/[+]!:uuid:8888)$do/$get/[=]!:uuid:1111#address
([+]!:uuid:9999/[+]!:uuid:8888)$do/#receipt/([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234
"there is a relationship between 9999 and 8888. in that relationship we have a link contract ($do). the link contract's associated #receipt is under ([=]!:uuid:1111/[+]!:uuid:9999)[#receipt]!:uuid:1234
Generic schema: (entity1/entity2) = Entity 1 and entity 2 have a relationship.
UUID:1234 = transaction receipt identifier
JSON signature
http://www.davedoesdev.com/json-web-signatures-on-node-js/
{
  "@context": "http://opennotice.org/spec/receipt-0.1",
  "receipt":{
    "timestamp": 1405243610859,
    "userId": "aweftrew",
    "dialogUrl": "http://michielbdejong.github.io/consent-receipt/signup.html",
    "dnt": true,
    "revokeUrl": "http://michielbdejong.github.io/consent-receipt/quit",
    "policyUrls": [
      "http://michielbdejong.github.io/consent-receipt/terms",
      "http://michielbdejong.github.io/consent-receipt/privacy"
    ]
  },
  "jsonSignature": "tr0tberoijawflekrjg5wrgtbghdfgrt09rtgjw5tbrthe5ztntr"
}
https://github.com/RDBinns/consent-receipt/blob/gh-pages/signup.html
http://on.smartspecies.com/consent-directory/form2.php
But how can Alice know, before going to the site to get the receipt that it is even a site that she is willing to trust to visit. Shouldn't there be at least the possibility for a pre-landing validation that the publishied notice for the site doesn't egregriously violate Alice's expectations?
The Open Notice Registry should provide the ability for a user/browser to validate basic notice BEFORE going to the site.
