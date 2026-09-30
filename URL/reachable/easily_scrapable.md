# Easily Scrapable (Reachable subset)

## 2026-09-16 session (30 URL batch)

- http://njstart.gov/ (redirects to NJSTART public portal; public open-bid/advanced-search pages load without login; one new qualifying finding saved on 2026-09-26 — see `Source/Scraped/2026-09-26_NJ-T2314-NJKiDS-Application-Maintenance-Support.md`)
- http://www.mncppc.org/register.html (redirects to M-NCPPC vendor resources; public procurement guidance and current IFB/RFP links load without login; no qualifying listing saved from this URL itself)
- https://a856-cityrecord.nyc.gov/ (public City Record procurement notices load without login; two qualifying NYC RFP records saved on 2026-09-16; re-checked 2026-09-26, only 2 current Solicitation-type notices site-wide, neither matched the approved keyword list)
- https://acwd.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire portal; only secondary-search evidence was available for IT-related items during this pass, so no file saved)
- https://alamedahsg.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire portal; no approved-keyword official listing saved in this pass)
- https://alexandriava.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire portal; secondary mirrors showed an IT-related RFP, but no directly verifiable official detail was available in this pass)
- https://algonquincollege.bonfirehub.ca/portal/?tab=openOpportunities (public Bonfire portal; no current approved-keyword official listing saved in this pass)
- https://alleghenycounty.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire portal; secondary mirrors showed an IT-related RFP, but no directly verifiable official detail was available in this pass)
- https://alohaebuys.hawaii.gov/bso/view/login/login.xhtml (public Aloha eBUYS advanced-search/open-bids pages load without login; one qualifying IT services record saved on 2026-09-16; re-checked 2026-09-26, 28 open bids reviewed, none matched the approved keyword list)

- https://www.scsk12.org/procurement/bids (redirects/alternate public Bids & RFPs page at `https://www.scsk12.org/procurement25/?PN=232`; public listings load without login; relevant staffing RFP saved on 2026-09-16; re-checked 2026-09-26, 8 open bids reviewed, none matched the approved keyword list)
- https://newhavenhousing.cobblestonesystems.com/gateway/Login.aspx (public CobbleStone solicitation/news pages are visible without login; reviewed visible current/recent solicitations on 2026-09-16 and found no approved-keyword match)

Scope: this file only covers the portion of `url_reachable.md` reviewed in the 2026-09-11 re-scrape session (rows 193 through the end of the list, ~168 URLs after the 5 not-applicable reclassifications). Rows 1–192 were scraped in an earlier session and are not classified here, except for the 5 rows added below on 2026-09-14.

"Easily scrapable" = the portal's RFP/bid listing (or search) loads and is readable without logging in, without solving a CAPTCHA, and without any other access barrier — even if the listing is currently empty.

## 2026-09-14 session (5 URLs sampled from rows 1-192)

- https://njstart.gov/ (redirects to `njstart.gov/bso/`; public "Open Bids" grid at `/bso/view/search/external/advancedSearchBid.xhtml?openBids=true`, 24 open state-issued bids — no keyword matches this pass)
- https://arkansas.ionwave.net/ (public "Current Bid Opportunities" grid at `/SourcingEvents.aspx?SourceType=1`, 10 open bids — only IT-adjacent item was an RFI, not an RFP)
- https://caleprocure.ca.gov/pages/Events-BS3/event-search.aspx (public Event Search, no login; keyword search works well — see `Source/Scraped/2026-09-14_RFP1053_Behavioral-Support-Staffing.md`)
- https://camisvr.co.la.ca.us/LACoBids/BidLookUp/OpenBidList (public keyword search across 223 open solicitations; IT-related hits found were RFSQ/IFB types, not RFP)
- https://a856-cityrecord.nyc.gov/ (public citywide notice search, no login; very high volume — 3000+ hits for "Information Technology" mixing Notices/Awards/Solicitations; later 2026-09-16 batch saved two relevant NYC RFP records)

## Bonfire / Euna Supplier Network portals (public "Open Opportunities" tab)

- https://sccpss.bonfirehub.com/portal/?tab=openOpportunities (re-checked 2026-09-30 with description/title review of all 4 open items — Document Destruction, CMR Services, Lawn Care, Design Professional Services — no approved-keyword match)
- https://scottsdaleaz.bonfirehub.com/portal/?tab=openOpportunities (re-checked 2026-09-30 — 5 open RFPs/RFSQ reviewed: diving/aerator maintenance, municipal financial advisor, CMAR waterline, green waste, benefits/EAP — no approved-keyword match)
- https://smctd.bonfirehub.com/portal/?tab=openOpportunities (specific opportunity linked from the original URL was closed, but the portal's open-opportunities tab is public; re-checked 2026-09-30, "There are no open projects at this time")
- https://strathcona.bonfirehub.ca/portal/?tab=openOpportunities (passes a brief Cloudflare check automatically; re-checked 2026-09-30 — 8 open items reviewed; "26.0059 GIS Consulting and Contracting Services" is a possible title-level match on "Scientific and Technical Consulting" but the detail page (opportunities/111181) is Cloudflare-blocked so scope could not be confirmed — not saved without confirmation; "26.0019 Integration Platform as a Service (iPaaS) Solution" title alone does not match an approved keyword; rest are infrastructure/fleet/roofing/concrete, no match)
- https://tohowater.bonfirehub.com/portal/?tab=openOpportunities (re-checked 2026-09-30 — 5 open IFB/RFQu items: surplus property, water main, catering, dewatering system, lift station equipment — no approved-keyword match)
- https://transitchicago.bonfirehub.com/portal/?tab=openOpportunities (re-checked 2026-09-30 — 9 open items reviewed; two are tagged Department "IT & Professional Services" (Duplo collator IFB, armored car service RFP) but that is only an internal department label — actual scope is office-equipment purchase and cash-transport/security services, not IT/staffing work, so not a workable match; rest are facilities/rolling-stock/construction, no match)
- https://ventura.bonfirehub.com/portal/?tab=openOpportunities (re-checked 2026-09-30 — 5 open items: youth crisis unit, culvert replacement, janitorial, specialty pharmacy, mental health rehab center — no approved-keyword match)
- https://waukeshacounty.bonfirehub.com/portal/?tab=openOpportunities (specific opportunity linked from the original URL was closed, but the portal's open-opportunities tab is public; re-checked 2026-09-30 — UPS/battery maintenance, snow removal — no approved-keyword match)
- https://wrd.bonfirehub.com/portal/?tab=openOpportunities (re-checked 2026-09-30 — only open item is "RFP-26-008: Drought Contingency Plan" — no approved-keyword match)
- https://yvr.bonfirehub.ca/portal/?tab=openOpportunities (re-checked 2026-09-30, "There are no open projects at this time")

## IonWave portals (public "Current Bid Opportunities" grid)

- https://sawsbid.ionwave.net/SourcingEvents.aspx?SourceType=1 (re-checked 2026-09-30 — 11 open items reviewed; two qualifying software licensing/support bids saved: `Source/Scraped/2026-09-30_SAWS-26-1310-Oracle-License-Renewal-DIR.md` and `Source/Scraped/2026-09-30_SAWS-26-1459-Adobe-Software-Licenses.md`; detail pages became Cloudflare-gated partway through the session so full scope/codes could not be confirmed beyond the listing row; rest of the 11 items are pipe/valve/truck/equipment purchases, no match)
- https://stillwater.ionwave.net/SourcingEvents.aspx?SourceType=1 (re-checked 2026-09-30 — 3 open IFBs: steel transmission poles, pavement management, pump station — no approved-keyword match)
- https://tarrantcountytx.ionwave.net/SourcingEvents.aspx?SourceType=1 (re-checked 2026-09-30 — 12 open items: hazmat response, grease-trap cleaning, transmission repair, refrigerants, glass repair, paper recycling, SWAT rifles, road base, trailers, brine systems, plows — no approved-keyword match)
- https://uiebid.ionwave.net/SourcingEvents.aspx?SourceType=1 (re-check 2026-09-30 found the portal now serves a Cloudflare "Performing security verification" interstitial instead of the bid grid; not bypassed per policy — see `blocked.md`)

## ProcureWare portals (public "Bids" grid)

- https://snoco.procureware.com/Bids (re-checked 2026-09-30 — reviewed first 50 of 1745 records with title/category-code review; two qualifying IT systems RFPs saved: `Source/Scraped/2026-09-30_Snohomish-RFP-26-0804BC-Training-Management-System.md` and `Source/Scraped/2026-09-30_Snohomish-RFP-26-0726BC-C-Online-Database-Reporting.md`; also noted but not saved: Cancelled "RFP-26-0791BC AI Governance Solution" and Cancelled "RFP-25-0606BC Web Design, Hosting and CMS Solution" (NIGP 920-series codes, would have matched, but status is Cancelled so not an active opportunity); narrative descriptions are gated behind vendor login, only titles/categories reviewed; remaining ~1695 records not exhaustively paged through given volume)
- https://stamfordct.procureware.com/home (real path: `/Bids`, 1187 records; re-checked 2026-09-30 — reviewed page 1 of ~24 pages (no working keyword filter found); previously-saved "2027.0084 City RFP - Enterprise SIP Trunking, PSTN, Numbering and 911 Services" still open (see `Source/Scraped/2026-09-11_City-of-Stamford-Enterprise-SIP-Trunking-RFP.md`); no other approved-keyword match on page 1; remaining pages not exhaustively reviewed given volume)

## PeopleSoft / Oracle Cloud supplier portals (public bidding-opportunity tile/grid)

- https://supplier.miamidade.gov/ ("Bidding Opportunities" tile → public grid; re-checked 2026-09-30 — all 20 open events reviewed by title/category; one qualifying software-licensing ITB saved: `Source/Scraped/2026-09-30_MiamiDade-ITB0000011-Adobe-Software-Licenses.md`; "Out of State Vehicle Registration Information" (Clerk of Courts) considered but detail page did not open and title alone is too ambiguous to confirm a match; rest are goods/construction/consulting-unrelated, no match)
- https://supplier.sok.ks.gov/psc/sokfsprdsup/SUPPLIER/ERP/c/SCP_PUBLIC_MENU_FL.SCP_PUB_BID_CMP_FL.GBL (42-row public grid; re-checked 2026-09-30 — all 33 currently-open events reviewed by title/description; three qualifying software/program-management systems saved: `Source/Scraped/2026-09-30_KS-EVT0010884-HR-Information-System.md`, `Source/Scraped/2026-09-30_KS-EVT0010915-Grant-Program-Manager.md`, `Source/Scraped/2026-09-30_KS-EVT0010854-Learning-Management-System.md`; "Online Marketplace Services" and "Student Loan Billing & Collection Support Services" considered but titles too ambiguous/off-scope to confirm a match without further description (login-gated); rest are unrelated goods/services)
- https://supplier.wmata.com/psc/supplier/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL? ("Active Solicitations" search, public; the homepage tile itself only opens via a blocked new-tab JS call, but its target page `https://supplier.wmata.com/psc/supplier_1/SUPPLIER/ERP/c/AUC_MANAGE_BIDS.AUC_RESP_INQ_AUC.GBL` loads directly and is public; re-checked 2026-09-30 — all 16 open/posted solicitations reviewed by title and (for plausible ones) full line-item detail; five qualifying IT systems RFPs saved: `Source/Scraped/2026-09-30_WMATA-0000010924-Counsel-Practice-Management-Software.md`, `Source/Scraped/2026-09-30_WMATA-0000010922-Emergency-Management-Platform.md`, `Source/Scraped/2026-09-30_WMATA-0000010927-ProWatch-System-Maintenance-Renewal.md`, `Source/Scraped/2026-09-30_WMATA-0000010941-MetroAccess-Fare-Collection-System.md`, `Source/Scraped/2026-09-30_WMATA-0000010918-MTPD-Background-Investigation-System.md`; "WMATA Consulting Service Agreement - GSA" considered but scope not specified beyond option years, too ambiguous to confirm a match; rest are non-IT goods/construction/maintenance, no match)
- https://vss.ky.gov/vssprod-ext/Advantage4 ("View Published Solicitations" tile → public grid, 20+ records; re-checked 2026-09-30 — all 40 currently-published solicitations reviewed across both pages by title/category; previously-saved "Network Security Software, Hardware, and Services" (RFB-758-2700000066-4) still open, same details, no update needed; two new qualifying items saved: `Source/Scraped/2026-09-30_KY-RFI-SAS-Enterprise-Financial-Reporting-Discovery.md` and `Source/Scraped/2026-09-30_KY-ACA-Recruiting-Coordinator.md`; rest are construction/equipment/medical/legal/education, no match; full narrative descriptions are login-gated on this portal)
- https://vss.ky.gov/vssprod-ext/Advantage4?openDoc=openDoc&DocumentCode=RFP&DepartmentCode=415&DocumentID=2600000199&DocumentVersNo=2&targetView=ammendHistoryView&Destination=pSolication (same portal)

## Periscope / BidSync family (public advanced-search results)

- https://sdbuynet.sandiegocounty.gov/page.aspx/en/usr/login (via "View Solicitations" link → public search/results, though downloading docs needs login; re-checked 2026-09-30 — reviewed first page (15) of 150+ open records sorted by begin date, plus keyword searches for "staffing" and "information technology" (both returned only historical Closed/Cancelled/Awarded hits, no currently-Open match); one qualifying HR-services RFP saved from the open listing: `Source/Scraped/2026-09-30_SanDiegoCounty-RFP-Classification-Compensation-Survey.md`; remaining ~135 open records across pages 2-7 not exhaustively paged given volume)
- https://www.bidbuy.illinois.gov/bso/external/vendor/regSummary.sdo?vendorId=NZdPl7Rvv_Oq&mode=initial&dateTime=1694627292171 (real search at `/bso/view/search/external/advancedSearchBid.xhtml?openBids=true`, now 175 open results; re-checked 2026-09-30 — reviewed page 1 of 7 (25 records) with full detail-page verification (including NIGP codes) for plausible IT/consulting candidates; one qualifying IFB saved: `Source/Scraped/2026-09-30_IL-MET10-Metro-Ethernet-IFB.md` (Metro Ethernet networking IFB, NIGP 838-xx); "Connect IL Implementation Tech Assistance" and "Tollway Technical Assistance Services" checked but are Type Code 55 Amendment/Change-Order notices to existing contracts, not new competitive solicitations, so not saved; remaining ~150 open records across pages 2-7 not exhaustively paged given volume)
- https://www.commbuys.com/bso/view/login/login.xhtml (real search at same path, 971 open bids; top-of-page keyword search box works well)

## Vendor-registry / small municipal planroom platforms

- https://vrapp.vendorregistry.com/Account/LogOn
- https://vrapp.vendorregistry.com/Bids/View/BidsList?BuyerId=c5e9d3e7-b8e0-4e36-bcab-8db00d18d769 (public list, currently empty)
- https://www.cpsk12bids.com/auth/login (via "Public Projects" link, ReproConnect platform)
- https://www.stlmsdplanroom.com/auth/login (via "Public Projects" link, ReproConnect platform, 15 pages of listings)
- https://www.rochesterhousing.org/bid-opportunities
- https://www.northwestmsbids.com/
- https://www.matawanborough.com/matawan/Bid%20Notices%20and%20Requests%20for%20Proposals/ (long public PDF list)
- https://www.annapolis.gov/bids.aspx
- https://www.ahfc.us/about-us/notices/requests-proposals
- https://www.cityoftulsa.org/government/departments/finance/selling-to-the-city/bid-opportunities-and-results/?t=current
- https://www.laramiecountywy.gov/Request-for-Proposals (redirects to a public BidNet Direct listing)
- https://www.bidnetdirect.com/new-jersey/lbha (public open-solicitations tab)
- https://www.myvendorlink.com/external/login (via "Bids" nav link → public multi-agency search, works well with Title keyword search)
- https://www.dcwater.com/useful-links (via "DC Water Solicitations" link → public Oracle Cloud solicitations list)

## Large public state/regional search engines (best keyword-search yield)

- https://vendor.purchasingconnection.ca/default.aspx (redirects to `purchasing.alberta.ca` — excellent public search engine, ~20,000 postings, real text-phrase filtering)
- https://www.instantmarkets.com/home (national aggregator, public keyword quick-filters, e.g. "Staffing" → 248 active results)
- https://www.txsmartbuy.gov/esbd (Texas statewide ESBD, public, 2,482 pages — keyword search box exists but did not reliably filter during this session)

## Other public listings

- https://purchasing.iu.edu/resources/forms/table.html (redirects to `procurement.iu.edu`; "Public Bid Postings" page and linked PDF are public)
- https://www.kcsdschools.net/dept/finance/procurement (loads without login; currently shows only contact info, no listings)
- https://www.voa.va.gov/default.aspx?PageId=1 (VA's public acquisition/industry-day resource hub — not a bid list, but loads freely)

## 2026-09-28 scheduled session (84 URL batch)

- https://apps.cupertino.org/details/756 (bid detail page renders server-side, no login; qualifying RFQ saved — see `Source/Scraped/2026-09-28_Cupertino-RFQ-for-Staff-Augmentation-Services.md`)
- https://bernco.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire portal; public AJAX endpoint `/PublicPortal/getOpenPublicOpportunitiesSectionData` returns real open solicitations without login; no approved-keyword match this pass)
- https://bgca.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire portal/AJAX endpoint accessible without login; currently empty open-opportunities list)
- https://bidlocker.us/Home/bidlockerus (public search at `/r/_/search` returns real listings without login; no genuine keyword match, only substring false positives)
- https://bidopportunities.chugachelectric.com/ (Drupal "Upcoming Bids and Contracts" view server-renders real entries without login; no approved-keyword match)
- https://bids.sciquest.com/apps/Router/PublicEvent?CustomerOrg=GIT (Georgia Tech Jaggaer "Business Opportunities" page server-renders real open events without login; no approved-keyword match)
- https://bids01.jaggaer.com/apps/Router/PublicEvent?CustomerOrg=Georgia&FromBranded=true (server-rendered "Open for Bid" listing, 37 results, no login; no approved-keyword match)
- https://bids01.jaggaer.com/apps/Router/PublicEvent?CustomerOrg=SUNY&FromBranded=true (server-rendered listing, 7 results, no login; no approved-keyword match)
- https://bids01.jaggaer.com/apps/Router/PublicEvent?CustomerOrg=UTSA&FromBranded=true (server-rendered "Current Solicitations" listing, no login; no approved-keyword match)
- https://cammnet.octa.net/ (public `/procurements` table server-renders without login; currently "Showing 0 Items" — current opportunities noted as moved to `procurement.opengov.com/portal/octa/`)
- https://dhr.alabama.gov/announcements/ (WordPress "Announcements & RFPs" list, 5 real items visible of 40 pages, no login; no approved-keyword match)
- https://ebs.pnnl.gov/advertised.aspx (PNNL "Advertised Solicitations" table server-renders 6 real rows without login; no approved-keyword match — all Construction/Goods/A-E)
- https://garwoodnj.govoffice3.com/index.asp?SEC=2E0FA122-5AAF-4709-8370-F01AB70B1579&pri=0 (server-renders a real "Notice to Bidders" list without login; no approved-keyword match)
- https://ggbhtd.bonfirehub.com/portal/ (public portal + AJAX endpoint returns real JSON, currently 0 open projects, no login required)
- https://habc.bonfirehub.com/portal/?tab=openOpportunities (public JSON endpoint returns 5 real open opportunities without login; no approved-keyword match in visible titles — e.g. "Website Maintenance and Support" is not itself an approved keyword)
- https://homesa.bonfirehub.com/portal/?tab=openOpportunities (public JSON endpoint returns 6 real open opportunities without login; no approved-keyword match — facilities/legal listings)

## 2026-09-29 session 2 (Bonfire/IonWave batch, browser-verified)

- https://iehp.bonfirehub.com/portal (open public opportunities table readable (e.g. 26-07372 Claims Editing Software - not a keyword match))
- https://jeffersoncitymo.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire listing readable without login; no approved-keyword match)
- https://lonestar.ionwave.net/SourcingEvents.aspx?SourceType=1 (7 open bids readable; none matched keywords)
- https://mdcourts.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire listing readable without login; no approved-keyword match)
- https://mdstad.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire listing readable without login; no approved-keyword match)
- https://menv.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire listing readable without login; no approved-keyword match)
- https://mps.bonfirehub.com/portal/?tab=openOpportunities (public grid readable; RFP 1180 Contingent Staffing Services saved (detail page behind Cloudflare))
- https://mwrd.bonfirehub.com/portal/?tab=openOpportunities (public Bonfire listing readable without login; no approved-keyword match)
- https://nait.bonfirehub.ca/portal/?tab=openOpportunities (public Bonfire listing readable without login; no approved-keyword match)
- https://nsc.bonfirehub.ca/portal/?tab=openOpportunities (public Bonfire listing readable without login; no approved-keyword match)
- https://pennbid.bonfirehub.com/portal/?tab=openOpportunities (PennBid public grid readable; no directly relevant IT/staffing match)
- https://pinalcountyaz.bonfirehub.com/portal (public Bonfire listing readable without login; no approved-keyword match)
