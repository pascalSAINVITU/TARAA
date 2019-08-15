# TARAA
The Attested Reputations Autonomous Agent

## Autonomous Agent Summary:
The AA deal with reputation of addresses (attested or not) in a given ‘Attested Domain’ and with a strategy for computing reputation. An ‘Attested Domain’ is composed of a ‘domain name’ paired to an ‘attestor address’.
Use cases:
One can request, for a minimal fee, the reputation of an address in an ‘attested domain’.
One can create a new ‘attested domain’ for a high fee.
One can contribute to the reputation of an address by sending an evaluation between ‘0’ and ‘5’ if he or she is attested by the related attestor.
One can change his/her evaluation later by voting again, the previous vote will be overrided.

## Additional information:
If no ‘domain’ is specify the default one is used: ‘base’
If no ‘attestor’ is defined the ‘real identity attestor’ will be used.
The gathered fees are used to reward the contributors who evaluate attested addresses. The reward is a pourcentage of a balance available for a given attestor scope, this will create a variable reward but insure that there will always be a reward available as small as it is. If the evaluated address is not attested the reward is symbolic or it will be too easy to empty the balance.
The hash of the address that created a domain is stored, so that creators can proove that they are the creator of the domain. (yeah but only once, should use the signature functionnality in next version)
A address cannot vote for itself.
SPAM and SCAMS
Cannot spam by creating much domains as it required a high fee
Cannot spam by making too much requests because it is not harming and there is also a small fee
Cannot emptying the ‘attestor scope balances’ because you need to be attested by the attestor of the attested domain and you can revote only every 30 days.

## Possible data input and Examples
data.domain aka data.do: optional <domain name> or ‘base’ will be use
data.attestor aka data.at: optional <Obyte attestor address> or default will be use
data.request aka data.re: <Obyte address object of the reputation request>
data.address aka data.ad: <Obyte address object of the evaluation>
data.evaluation aka data.ev: [0–5]
data.creation aka data.cr: [uwa, twa, crwa, cbwa] to create a new Attested Domain (it will require ‘data.domain’ and ‘data.attestor’) <uwa> will use ‘Un-Weighted Average’, <twa> for ‘Time Weighted Average’, <rwa> for ‘Contributor Reputation weighted Average’ and <cbwa> for ‘Contributor Balance Weighted Average’
  
### Example 1: Requesting the reputation of the adress ‘MPG4MHVYUAP3B5IQX44LTINTSUKYB6JA’ in the Default Attested Domain (‘DAD’)
send 20000 bytes (10000 for min bounce + 10000 as fee for the attestor balance in the AA)
to the adress of the AA
data.request = MPG4MHVYUAP3B5IQX44LTINTSUKYB6JA (you could use data.ad for shorter)
### Example 2.1: Contribute to a reputation by voting 3/5 for the address ‘MPG4MHVYUAP3B5IQX44LTINTSUKYB6JA’ in the ‘DAD’
send to TARAA 10000 bytes (10000 for min bounce fee)
data.address = MPG4MHVYUAP3B5IQX44LTINTSUKYB6JA
data.evaluation = 3 (or [0–5])
### Example 2.2: Replacing your vote for the address ‘MPG4MHVYUAP3B5IQX44LTINTSUKYB6JA’ in the ‘DAD’
send to TARAA 10000 bytes (10000 for min bounce fee)
data.address = MPG4MHVYUAP3B5IQX44LTINTSUKYB6JA
data.evaluation = 4
### Example 3: create a new attested domain with the UWA mode called ‘Obay’ and attested by ‘35IT3ZYKEPQSCXG2F7A7KWNRAD3SZXN4’
send to TARAA 510000 bytes (10,000.0 for min bounce fee and 500,000.0 for the creation fee)
data.creation = uwa
data.domain = obay
data.attestor = 35IT3ZYKEPQSCXG2F7A7KWNRAD3SZXN4
