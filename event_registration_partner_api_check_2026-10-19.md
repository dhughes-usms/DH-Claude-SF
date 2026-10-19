# Event registration data from partner APIs: Salesforce check (Oct 19, 2026)

Read-only SOQL through the USMS connector, run 2026-10-19.

## Headline

**Salesforce holds no per-event registration data from any partner.** The `EventRegistration__c`
object (Member, USMS Sanction, Registration Date) exists and has the right shape for a partner feed,
but contains **0 records**, ever. A count of zero was confirmed against the connector's rendering
(it shows "0 rows" for a zero count and "COUNT() = n" otherwise).

What Salesforce does carry is the **Event License Add-on** (product code COMPREG), a $0 line item on
a member's registration that says the member may enter sanctioned events. It is not tied to any
event or partner.

## Event License Add-on (2026 registration year)

| Measure | Value |
|---|---|
| Event License lines, 2026 reg year | 33,816 (18 refunded) |
| Created by the registration-system integration user | 33,799 (99.95%) |
| Created by staff users (manual) | 17 |
| Attached at initial registration | 28,444 |
| Attached as a later add-on | 5,355 |
| Later add-ons since July 2026 | 77 (14 / 22 / 39 / 2 by month) |
| Last record created | 2026-10-19 11:56 UTC |
| Lines missing a member registration or date | 0 |
| Lines with no transaction ID | 2,000+ (free line, no payment; not an error) |

Monthly volume follows the membership season (7,922 in Nov 2025, 10,464 in Dec, 6,003 in Jan,
~1,000 to 1,200 a month Jun to Sep). The later "Add-on" path, which is the one a partner site would
push a member through when they lack a license, is small and shrinking: 2,487 in Nov 2025 down to
2 so far in October.

Transaction IDs fall into two numeric families (last 30 days: 796 starting "1218…", 69 starting
"818…", 6 other). These are payment-processor IDs, not partner identifiers; nothing on the record
names Club Assistant, RunSignUp, or any other partner.

## Events flagged as using a partner platform

Among 2026 sanctioned events, the sanction form asks "Event using Club Assistant or RunSignUp" and
"Offering One Event Registrations (OEVTs)".

| Partner platform | OEVT yes | OEVT no | OEVT blank |
|---|---|---|---|
| Yes | 25 | 172 | 95 |
| No | 2 | 98 | 30 |
| Blank | 0 | 6 | 210 |

The 25 "yes / yes" events are all open-water swims (Lake Berryessa, Santa Cruz, Swim the Suck,
Lake Cumberland, Chicago River Swim, and others). None of their entries appear anywhere in
Salesforce. Entry counts live only on the partner sites.

## What this means

- Partner APIs today only **verify** membership and event-license status; they do not **write**
  registrations back. If a write-back integration was expected, it has never fired.
- There is no way in Salesforce to answer "how many members entered event X" or "how many entries
  came through RunSignUp vs Club Assistant".
- The only event-related signal that is flowing is the Event License Add-on, and that feed is
  healthy: current to today, complete, one integration user.

## To make partner registrations visible

1. Confirm with the partners (Club Assistant, RunSignUp, SwimPhone or others) whether their USMS
   API integration includes a registration push, and to which endpoint.
2. If it does, the target should be `EventRegistration__c` with Member, USMS Sanction and date; add
   a Source/Partner field so feeds can be told apart.
3. If it does not, the alternative is a periodic entry-file import per sanctioned event.
