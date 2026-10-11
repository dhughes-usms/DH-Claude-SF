# Metropolitan LMSC: live Salesforce (Oct 11, 2026) vs. Oct 8 Drive extract

Live figures come from read-only Salesforce queries run through the USMS connector on 2026-10-11.
Extract figures come from the CSVs saved to Drive on 2026-10-08 (`lmsc_members_by_year.csv`,
`club_members_by_year.csv`, `sanctions.csv` in the Relay ROI data folder).

## How the two sources count members

- **Extract:** one club per member per registration year. The club rows sum exactly to the LMSC total
  (1,757 / 1,461 / 1,311), so a member who transferred mid-year is credited to a single club.
- **Live "registrations" column:** distinct members with a non-refunded registration record in the year,
  per club. A member who registered with two Metropolitan clubs in the same year appears under both,
  so club rows sum to more than the LMSC total. Transfer-in/transfer-out rows are the main cause.
- **Live "current club" column (2026 only):** members whose latest registration year is 2026, by the club
  on their member record today. This is the closest apples-to-apples to the extract.

## LMSC totals

| Registration year | Extract (Oct 8) | Live distinct members | Live registration rows | Live by current club |
|---|---|---|---|---|
| 2024 | 1,757 | 1,767 | 1,868 | – |
| 2025 | 1,461 | 1,474 | 1,553 | – |
| 2026 (through Oct 11) | 1,311 | 1,325 | 1,475 | 1,310 |

The 10 to 14 member gap between the extract and the live distinct count is methodological, not new
registrations: 2024 and 2025 are closed years and still differ. The extract's exact rule is not documented
in the files. The 2026 current-club figure (1,310) matches the extract (1,311) within one member.

2026 registration mix (non-refunded rows): 1,177 new registrations, 132 conversions, 107 add-ons,
27 transfers in, 26 transfers out. Only 5 refunded registrations in 2026.

## Members by club: extract vs. live

Format: `extract → live (difference)`; a single number means both agree. Last column is the live
current-club count for 2026.

| Club | 2024 | 2025 | 2026 | 2026 current club |
|---|---|---|---|---|
| AGUA Masters (AGUA) | 136 → 140 (+4) | 143 → 151 (+8) | 168 → 175 (+7) | 171 |
| Bard Swim Club (BSC) | 4 → 5 (+1) | 1 | – | – |
| Bay Ridge Masters (BRAT) | 27 → 28 (+1) | 30 | 28 | 28 |
| Bearcat Masters (BCTM) | 23 → 26 (+3) | 21 → 23 (+2) | 14 | 11 |
| Brooklyn College Masters Swim (BKLNS) | – | – | 2 | 2 |
| Chelsea Piers Fitness NY/BK (CHEL) | 46 → 48 (+2) | 42 | 42 → 43 (+1) | 41 |
| Columbia Tri (CTRI) | 37 | 26 | 26 → 28 (+2) | 27 |
| East End Masters (EEM) | 9 → 10 (+1) | 12 | 8 | 8 |
| Freedom Aquatics (FREE) | – | 1 | 3 | 3 |
| Front Runners New York (FRNY) | 88 | 92 | – | – |
| Hudson Valley Dolphins (HVD) | 50 | 58 → 59 (+1) | 57 → 58 (+1) | 58 |
| Iron Fit Endurance (IA) | 34 | 21 | 26 | 26 |
| Long Island City YMCA Masters (LICY) | 11 | 7 | 8 → 9 (+1) | 8 |
| Long Island Express Masters (EXMS) | 36 | 42 | 45 → 46 (+1) | 46 |
| Marlins Masters (BGNW) | 11 | 12 | – | – |
| Match Point NYC Masters (MPNY) | 2 | 2 | 3 | 3 |
| McBurney YMCA Masters (BURN) | 29 → 30 (+1) | 20 → 21 (+1) | 21 | 21 |
| Metro Masters Swim Club (METR) | 19 | 16 → 18 (+2) | 14 | 14 |
| New York Athletic Club (NYAC) | 55 | 63 | 69 | 69 |
| NYC Hydras (NYCH) | 97 → 100 (+3) | 80 | – | – |
| Patriot Swim Team (PATZ) | 10 → 15 (+5) | 35 → 36 (+1) | 15 → 20 (+5) | 18 |
| Peconic Masters Swim Club (PMSC) | 10 | 8 | 8 | 8 |
| Phoenix Aquatic Club (PAC) | 14 | 10 | 5 | 5 |
| Pineapples (PINE) | 28 → 30 (+2) | 31 → 37 (+6) | 16 → 20 (+4) | 19 |
| QNS Masters (QNS) | 3 → 4 (+1) | 8 → 9 (+1) | 1 | 1 |
| Red Tide (REDT) | 155 → 158 (+3) | 136 → 139 (+3) | 174 → 175 (+1) | 172 |
| Sunrise Swimmers (SEAW) | 35 → 37 (+2) | 43 → 44 (+1) | 36 → 37 (+1) | 37 |
| Swim Unattached (club record, UN) | – | – | 3 | 3 |
| Team New York Aquatics (TNYA) | 368 → 375 (+7) | 156 → 158 (+2) | 124 → 126 (+2) | 124 |
| Total Masters Swimming (TS) | 50 | 42 | 30 | 30 |
| Train Daly (TDALY) | 2 | 2 | 3 | 3 |
| Trident Aquatic Club (TRDNT) | 8 → 10 (+2) | 5 | 2 | 2 |
| Unattached - Metropolitan (UC6) | 305 → 309 (+4) | 234 → 237 (+3) | 301 → 305 (+4) | 292 |
| Yonkers Masters (YM) | 55 → 62 (+7) | 62 → 63 (+1) | 59 → 60 (+1) | 60 |

Every difference is live ≥ extract and concentrated in clubs that receive transfers (AGUA, Pineapples,
Patriot, Yonkers, TNYA, Red Tide, unattached). No club lost members between Oct 8 and Oct 11.
Real movement since Oct 8 shows in the current-club column: unattached dropped from 301 to 292 while AGUA,
Patriot and Pineapples each picked up about three, consistent with unattached swimmers joining clubs.

## Clubs with 2025 members and no 2026 member registrations

| Club | 2025 members | Club registration status | Note |
|---|---|---|---|
| Front Runners New York (FRNY) | 92 | Lapsed, last club registration 2025 | Largest loss in the LMSC |
| NYC Hydras (NYCH) | 80 | Lapsed, last club registration 2025 | Workout groups allowed, none attached |
| Marlins Masters (BGNW) | 12 | Renewed for 2026 (Sept 11, 2026) and 2027 (Oct 1, 2026) | Club is registered but has zero 2026 member registrations |
| Bard Swim Club (BSC) | 1 | Lapsed, last club registration 2024 | |
| Rye YMCA (RYEY) | 0 | Registered 2025, lapsed | Never had member registrations in 2025 or 2026 |

Both sources agree on this list. Live and extract are identical for FRNY, NYCH, BGNW and BSC.

## Club registrations (ClubRegistration__c)

- 2026 club registrations: 31 clubs (Marlins' 2026 registration was recorded on 2026-09-11, the only one
  dated after June).
- 2027 renewals already in as of Oct 11: 11 clubs. AGUA, Bearcat, Chelsea Piers, Freedom Aquatics,
  Hudson Valley Dolphins, LaneMate, Marlins, NYAC, Swim Unattached (UN), TNYA, Yonkers.
- Oddities worth a look: LaneMate (LMATE) is a Sarasota, Florida affiliate registered under the
  Metropolitan LMSC with zero members. "Swim Unattached" (UN) is a Member Club record in East Meadow
  carrying 3 members, separate from the real unattached bucket (UC6).

## Workout groups

Salesforce models workout groups as club records whose members carry a parent club (for example
Life Time Swim Alpharetta under LTMS in Georgia). No Metropolitan member with a 2026 registration has a
parent club, so **Metropolitan has no active workout groups in Salesforce**. Eight clubs are flagged
"workout groups allowed" (Columbia Tri, Iron Fit, LIC YMCA, Metro Masters, NYC Hydras, Patriot, Phoenix,
Pineapples) but none has a group attached. The only workout-group-named records in the LMSC are
Brooklyn Heights Workout Group (lapsed 2015) and Terriers Workout Group (lapsed 2013).
The Oct 8 extract has no workout group file, so there is nothing to compare.

## Upcoming Metropolitan sanctions (start date on or after Oct 11, 2026)

| Event | Date | Classification | Status | Course | City | Sanction ID |
|---|---|---|---|---|---|---|
| Dr. Bill Ross Memorial Masters Swim Meet | 2026-11-22 | Sanctioned | Published | SCM | East Meadow | 066-S007 |
| Dr. Bill Ross Memorial Masters Meet | 2026-11-22 | Calendar | Published | SCM | East Meadow | none (duplicate calendar listing) |
| Aquapalooza VII (TNYA) | 2027-04-17 | Recognized | Published | SCM | Bronx | 067-R003 |
| Aquapalooza VII (TNYA) | 2027-04-17 | Recognized | Incomplete | SCM | Bronx | draft duplicate |
| Aquapalooza (TNYA) | 2027-04-17 | Recognized | Incomplete | SCM | Bronx | draft duplicate |

The extract (Oct 8) holds the same 5 upcoming records and the same 17 Metropolitan records overall for
2025 to 2027; nothing was added, cancelled or published between Oct 8 and Oct 11. The public usms.org
calendar shows only the two published events (Bill Ross, Aquapalooza VII). The Bill Ross calendar
duplicate and the two Incomplete Aquapalooza drafts are housekeeping items.

Earlier 2026 Metropolitan events for reference: Metro SCY Champs at AGUA (Apr 4), Metro SCY
Championships (Apr 12), Jason Troiano Memorial in Yonkers (Apr 18, cancelled), Aquapalooza VI (May 2),
and two Swim Across America open water listings (Jul 25, Aug 1).
