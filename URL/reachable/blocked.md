# Blocked (Reachable subset)

## Login / registration / session pages reviewed on 2026-09-26

- http://www.morriscountybidsystem.com/ (redirects to `https://www.bidnetdirect.com/new-jersey`; server responds 200 with a real BidNet Direct marketing/landing page, but the page contains no bid-listing content — only "Login"/"Register" links — so no solicitation data is viewable without a BidNet account; reclassified from `easily_scrapable.md` after re-check)

## Login / registration / session pages reviewed on 2026-09-16

- http://procurement.opengov.com/ (redirects to generic OpenGov Procurement login; no agency project grid visible at this root URL)
- http://vendorportal.dc.gov/ (redirects to DC invoicing vendor login; page notes bidding remains elsewhere, no solicitation listing visible)
- https://access.alberta.ca/auth/realms/41898876-5358-402d-aae5-eee17a413de5/protocol/openid-connect/auth?client_id=apc-app&redirect_uri=https%3A%2F%2Fpurchasing.alberta.ca%2Fauth-callback&response_type=code&scope=openid&state=bbfd4bd389cb423a98165473274390b5&code_challenge=7gPvK1m6Ml4-FdLaOsGEF5qqfo6D4i1z5YQag7pazSY&code_challenge_method=S256&response_mode=query&apc_target=supplier (Alberta account-authentication URL; public purchasing search exists elsewhere, but this URL is an authentication flow)
- https://account.bonfirehub.com/login?flow=e128e6d0-9c89-447a-a993-8965998b25cf (generic Bonfire account login, not a public opportunities tab)
- https://alabamabuys.gov/page.aspx/en/sup/registration_extranet/save (supplier-registration flow, no solicitation listing visible)
- https://alabamabuys.gov/page.aspx/en/usr/login (Alabama Buys login page; no public solicitation results visible at this URL)
- https://allentx.ionwave.net/Vendor/VendorHome.aspx (IonWave vendor-home/login area; public sourcing-events grid was not confirmed from this URL in this pass)
- https://app.az.gov/page.aspx/en/sup/registration_extranet/save (supplier-registration flow, no solicitation listing visible)
- https://app01.jaggaer.com/apps/Router/BrandedSupplierHome?CustOrg=GIT&supplierID=1007876976&tmstmp=1763649218182 (JAGGAER supplier/session URL, no public solicitation listing visible)
- https://app01.jaggaer.com/apps/Router/BrandedSupplierHome?CustOrg=UMich&supplierID=1007876976&tmstmp=1750096171684 (JAGGAER supplier/session URL, no public solicitation listing visible)
- https://app01.jaggaer.com/apps/Router/BrandedSupplierHome?tmstmp=1733233768378 (JAGGAER supplier/session URL, no public solicitation listing visible)
- https://app01.jaggaer.com/apps/Router/BrandedSupplierHome?tmstmp=1757684588373 (JAGGAER supplier/session URL, no public solicitation listing visible)
- https://app01.jaggaer.com/apps/Router/BrandedSupplierHome?tmstmp=1768591824093 (JAGGAER supplier/session URL, no public solicitation listing visible)
- https://app01.jaggaer.com/apps/Router/BrandedSupplierHome?tmstmp=1769709497801 (JAGGAER supplier/session URL, no public solicitation listing visible)
- https://app01.jaggaer.com/apps/Router/BrandedSupplierHome?tmstmp=1782391392219 (JAGGAER supplier/session URL, no public solicitation listing visible)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=CalState (JAGGAER supplier login URL, no public solicitation listing visible)

Scope: this file only covers the portion of `url_reachable.md` reviewed in the 2026-09-11 re-scrape session (rows 193 through the end of the list). Rows 1–192 were scraped in an earlier session and are not classified here.

"Blocked" here means the URL still counts as reachable (the server responds), but no RFP/solicitation content could actually be viewed — because of a login wall, a CAPTCHA/bot-check, a Cloudflare block, a broken/error page, or a paywall. Per policy, no login was attempted and no CAPTCHA was solved.

## Login required (no public bid list found)

- https://norta.procureware.com/login (ProcureWare login/registration gate for solicitation documents; related public LaPAC listing was visible separately and relevant IFB was saved on 2026-09-16)
- https://procurement.opengov.com/vendors/155272/proposal
- https://secure.bidsandtenders.ca/Module/Tenders/en/Login/Index/
- https://security.app.cpa.state.tx.us/Public/login?logout
- https://service.ariba.com/Authenticator.aw/ad/ssoIDP
- https://sigma.michigan.gov/PRDVSS1X1/Advantage4 (public tiles present are Register/Announcements/Vendor Guides/Vendor Forms/Grant Opportunities only — no bid-search tile was found, though the carousel was not fully exhausted)
- https://sms-idaho-prd.tam.inforgov.com/sso/SSOServlet?_action=LOGINREQD&... (Infor SSO)
- https://sms-idaho-prd.tam.inforgov.com/sso/SSOServlet?_action=TIMEOUTASSERT&... (same portal)
- https://sms-nola-prd.inforcloudsuite.com/fsm/SupplyManagementSupplier/page/XiSupplyManagementSupplierPage?csk.SupplierGroup=100 (page hung on "Loading..." and never resolved)
- https://solutions.sciquest.com/apps/Router/BrandedSupplierHome?CustOrg=UCOP&supplierID=1007876976&tmstmp=1738093109276 (broken session / bookmark error)
- https://solutions.sciquest.com/apps/Router/SupplierLogin (generic)
- https://solutions.sciquest.com/apps/Router/SupplierLogin?CustOrg=BridgewaterState
- https://solutions.sciquest.com/apps/Router/SupplierLogin?CustOrg=DASIowa
- https://solutions.sciquest.com/apps/Router/SupplierLogin?CustOrg=Princeton&isLogout=true&tmstmp=1716220417643
- https://solutions.sciquest.com/apps/Router/SupplierLogin?CustOrg=StateOfUtah&isLogout=true&tmstmp=1699984786288
- https://solutions.sciquest.com/apps/Router/SupplierLogin?GSPSupplier_Login_Email=Business-development%40ommincorp.com&CustOrg=StateOfMontana&SuccessToken=1&tmstmp=1695233574600
- https://solutions.sciquest.com/apps/Router/SupplierPortalHome?tmstmp=1699981963442
- https://solutions.sciquest.com/apps/Router/SupplierWelcome?CustOrg=TriMet&supplierID=1007876976&tmstmp=1704204983800
- https://stamfordct.procureware.com/login (the portal's home/`/Bids` path is public — this specific login path is not)
- https://supplier.esmsolutions.com/home (redirects to ESM Solutions login)
- https://supplier.ionwave.net/Vendor/VendorHome.aspx
- https://supplier.ionwave.net/VendorLogin.aspx
- https://supplier.ionwave.net/VendorResponse/ResponseList.aspx?status=AVAILABLE
- https://supplierservice.sanantonio.gov/irj/portal (SAP NetWeaver login)
- https://supplierservice.sanantonio.gov/irj/portal#12587465-vendor-info (same)
- https://upstream.dc.gov/Sourcing/Main/ad/loginPage/SSOActions?... (Ariba login)
- https://upstream.dc.gov/Sourcing/Main?realm=System&passwordadapter=SourcingSupplierUser&awsso_tkn=24MUzqrzky68f28a69a52257ff (same, Ariba)
- https://vendor.myfloridamarketplace.com/login
- https://vendorportal.dc.gov/Account/Login (invoicing portal only; no bid list)
- https://www.bidnetdirect.com/private/supplier/solicitations/search (SSO login)
- https://www.californiabids.com/bid_opportunities/ (only historical award results are public; live search requires login/registration)
- https://www.demandstar.com/app/suppliers/bids
- https://www.infotechexpress.com/business
- https://www.mymta.info/psc/VENDOR/GUEST/SUPP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL? (only Sign-In/Registration tiles; no public bid list found)
- https://www.mymta.info/psc/VENDOR/SUPPLIER/SUPP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL?... (same portal)
- https://www.njstart.gov/bso/external/vendor/regComSrvcCodes.sdo (500 server error)
- https://www.nunavuttenders.ca/UploadBidderTC.aspx (redirects to login, "Bidder Login")
- https://www.rfpmart.com/userlogin.html (real RFP categories exist, e.g. "038 - Staffing Services," but actual listings are gated behind login/CAPTCHA)

## CAPTCHA / bot-check walled (not bypassed, per policy)

- https://trstexas-supplier.ivalua.app/page.aspx/en/sup/registration_manage/2594 (browser-check CAPTCHA)
- https://vtbuys.suppliers.vermont.gov/page.aspx/en/usr/login (browser-check CAPTCHA)
- https://vendors.planetbids.com/ ("Human Verification" bot-check; confirmed on this URL and one sampled portal ID — all ~40 PlanetBids URLs below share this domain and are presumed blocked the same way, not individually re-tested)
  - https://vendors.planetbids.com/portal/14599/bo/bo-search
  - https://vendors.planetbids.com/portal/14599/portal-home
  - https://vendors.planetbids.com/portal/15300/portal-home
  - https://vendors.planetbids.com/portal/15381/portal-home
  - https://vendors.planetbids.com/portal/16151/portal-home
  - https://vendors.planetbids.com/portal/16151/vp/vp-home
  - https://vendors.planetbids.com/portal/16725/login
  - https://vendors.planetbids.com/portal/17950/login
  - https://vendors.planetbids.com/portal/17950/login#
  - https://vendors.planetbids.com/portal/20134/portal-home
  - https://vendors.planetbids.com/portal/20136/vp/vp-home
  - https://vendors.planetbids.com/portal/20314/portal-home
  - https://vendors.planetbids.com/portal/22078/portal-home
  - https://vendors.planetbids.com/portal/22576/bo/bo-detail/141899
  - https://vendors.planetbids.com/portal/23532/bo/bo-search
  - https://vendors.planetbids.com/portal/23758/portal-home
  - https://vendors.planetbids.com/portal/24103/portal-home
  - https://vendors.planetbids.com/portal/24660/portal-home
  - https://vendors.planetbids.com/portal/24661/portal-home
  - https://vendors.planetbids.com/portal/27996/portal-home
  - https://vendors.planetbids.com/portal/28789/portal-home
  - https://vendors.planetbids.com/portal/29744/portal-home
  - https://vendors.planetbids.com/portal/32621/vp/vp-home
  - https://vendors.planetbids.com/portal/39475/vp/vp-home
  - https://vendors.planetbids.com/portal/39495/login
  - https://vendors.planetbids.com/portal/39495/login#
  - https://vendors.planetbids.com/portal/39501/portal-home
  - https://vendors.planetbids.com/portal/43728/vp/vp-home
  - https://vendors.planetbids.com/portal/45619/bo/bo-search
  - https://vendors.planetbids.com/portal/49906/vp/vp-home
  - https://vendors.planetbids.com/portal/53010/portal-home
  - https://vendors.planetbids.com/portal/59724/vp/vp-home
  - https://vendors.planetbids.com/portal/62287/bo/bo-search
  - https://vendors.planetbids.com/portal/64863/portal-home
  - https://vendors.planetbids.com/portal/65292/vp/vp-prereg
  - https://vendors.planetbids.com/portal/65844/portal-home
  - https://vendors.planetbids.com/portal/68007/portal-home
  - https://vendors.planetbids.com/portal/76708/portal-home
  - https://vendors.planetbids.com/portal/77636/portal-home
  - https://www.beaconbid.com/solicitations/city-of-houston/121f4067-fb3a-4d30-85b9-ea6a6cafe989/contingent-labor-services-all-categories?token=supplier-login.ObiU4vtGsc_vRNVc-a87JReydRqhQP07ozrco4z95xclrg1KaW517ezRNB5QzTvK8dS9z_wfmREHNc6qRuGr-uHTYI229n9X2AhzK2_xmpo1LIlDsnrcN9YzPY9tkrWfy3EN_v3vttW09t3yqiaBnArwIvYLa3JnzE4G9B1giu5p7FuxEHf2iImOzrCy7TDIptzKNwKUivDO0G3DxgJ4Yz43Iz6gCzrsPGyOdGXCJV9Qg29rKw2IN4_Nw5d1czIABi6VfJW2RJtyEc02dHo1amlJHrAnTsWOtrQ8zz6lolxc5u8OanNPWUJnmTMDrOPoY-3_mtuNxCYeyzX2seLpWEfkAtq1AbX1X_Xb-492Ng&eid=bc055432-0873-482a-98b8-0490d2821dc8 (URL itself contains a supplier-login token; not individually tested)

## 2026-09-30 re-check: OpenGov platform now Cloudflare-gated (previously easily scrapable)

The entire `procurement.opengov.com` platform, previously recorded in `easily_scrapable.md` as loading a public "Projects" grid without login, now serves a Cloudflare "Performing security verification" interstitial with an interactive "Verify you are human" (Turnstile) checkbox on every portal tested. Confirmed individually on 7 of the 27 URLs below (aurorail, baltimorecountymd, bft, bloomingtonin, brevardschools, cityoftampa, rtd-denver) after a 3-5s wait each; per policy no CAPTCHA was clicked/solved. The remaining 20 share the identical `procurement.opengov.com/portal/<slug>` pattern and identical Cloudflare challenge markup, so they are recorded here as a confirmed family rather than individually re-tested. Moved from `easily_scrapable.md` to here on 2026-09-30.

- https://procurement.opengov.com/portal/aurorail
- https://procurement.opengov.com/portal/baltimorecountymd
- https://procurement.opengov.com/portal/bft
- https://procurement.opengov.com/portal/bloomingtonin
- https://procurement.opengov.com/portal/brevardschools
- https://procurement.opengov.com/portal/cheyennecity
- https://procurement.opengov.com/portal/cityofbradenton
- https://procurement.opengov.com/portal/cityofedinburg
- https://procurement.opengov.com/portal/cityofhomestead
- https://procurement.opengov.com/portal/cityofnsb
- https://procurement.opengov.com/portal/cityoftampa
- https://procurement.opengov.com/portal/clevelandoh
- https://procurement.opengov.com/portal/co-hidalgo-tx
- https://procurement.opengov.com/portal/lompoc
- https://procurement.opengov.com/portal/morenovalley
- https://procurement.opengov.com/portal/oak-brook
- https://procurement.opengov.com/portal/pasadena
- https://procurement.opengov.com/portal/pinoleca
- https://procurement.opengov.com/portal/rtd-denver
- https://procurement.opengov.com/portal/saccounty
- https://procurement.opengov.com/portal/santacruzca
- https://procurement.opengov.com/portal/smcgov
- https://procurement.opengov.com/portal/stpete
- https://procurement.opengov.com/portal/tucson-az
- https://procurement.opengov.com/portal/tuolumnecountyca
- https://procurement.opengov.com/portal/wheatridgeco
- https://www.frederickcountymd.gov/1116/Open-Bids---Current-Solicitations (redirects to `procurement.opengov.com/portal/frederickcountymd`, same Cloudflare challenge)

## 2026-09-30 re-check: reclassified from easily_scrapable.md (login page, not a listing)

- https://vrapp.vendorregistry.com/Account/LogOn (generic Vendor Registry login page, no bid-listing content of its own; the platform's actual public listing is `https://vrapp.vendorregistry.com/Bids/View/BidsList?BuyerId=...`, which remains in `easily_scrapable.md`)

## 2026-09-30 re-check: reachable URL now blocked (moved from easily_scrapable.md)

- https://www.laramiecountywy.gov/Request-for-Proposals (previously redirected to a public BidNet Direct listing; now returns an Akamai edge "Access Denied" block on this server, reference #18.6102817...)

## 2026-09-30 re-check: additional platform now Cloudflare-gated

- https://uiebid.ionwave.net/SourcingEvents.aspx?SourceType=1 (previously recorded in `easily_scrapable.md` as a public IonWave grid; on 2026-09-30 re-check it now serves a Cloudflare "Performing security verification" interstitial instead of the bid list — moved here)

## Cloudflare / WAF blocked

- https://www.cdta.org/node/15813/register ("Access denied")
- https://www.centralauctionhouse.com/login.php (Cloudflare "Sorry, you have been blocked")
- https://www.govevents.com/?signoutsucccess (Cloudflare "Sorry, you have been blocked")
- https://www.mecknc.gov/finance/procurement/Pages/default.aspx (Cloudflare "Sorry, you have been blocked")
- https://recuperacion.pr.gov/en/procurement-and-nofa/procurement/ ("The request is blocked")
- https://via.sbecompliance.com/ (403 Forbidden)
- https://via.sbecompliance.com/?TN=via (403 Forbidden)

## Broken / error pages

- https://via.diversitycompliance.com/FrontPage/VendorMain.asp?XID=9510 (404 - File or directory not found)
- https://www.nyscr.ny.gov/login.cfm (404, error frame)

## Uncertain / could not confirm a working listing this session

- https://www.kalcounty.com/ (redirects to kalcounty.gov; site loads but no bid/RFP page was successfully located via its search)
- https://www.bidexpress.com/businesses/85766/home?agency=true (agency page loads; the "Solicitations" nav link did not successfully load a listing, and a guessed `/solicitations` path 404'd)
- https://www.ptcvendorportal.com/ (homepage shows a public "Latest RFxs" link, but clicking it did not navigate to any content in this session)

## 2026-09-28 scheduled session (84 URL batch)

No JS-rendering browser was available this session (headless Chromium could not be made to trust the environment's proxy TLS certificate); all checks below used `curl`/`WebFetch` against raw server responses. No login was attempted anywhere despite `URL/State Portals Credentials.xlsx` existing.

### Login / SSO / registration wall

- http://newhavenhousing.cobblestonesystems.com/gateway/Login.aspx (Cobblestone "Welcome & Sign In" wall, no RFP content pre-auth)
- https://bids.wyomingmi.gov/Bid/SpecDownload/2236?fromLogin=1 (redirects to a Home/Login sign-in page, no bid content viewable without auth)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=CalState... (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=DASIowa... (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=FSU... (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=MDAndersonPS (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=StateOfNewMexico (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=TAMU (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=TriC (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=UConnFullSuite... (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=UIdaho (Jaggaer supplier-login wall)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=URI (Jaggaer supplier-login wall; all 10 Jaggaer SupplierLogin URLs above render the identical login shell verbatim — platform-wide pattern, only representative bodies diffed in full)
- https://arbuy.arkansas.gov/bso/view/login/login.xhtml (JSF login form)
- https://baltimorecity.diversitycompliance.com/FrontPage/VendorMain.asp?XID=2708 ("You've been logged out", redirects to login)
- https://bidportal.ksu.edu/Module/Tenders/en/Vendor/Dashboard/70f4d5cf-dabf-47c6-a618-3522733a7088 (resolves to Kansas State Bid Portal login form)
- https://brazosbid.ionwave.net/Login.aspx (IonWave login/registration page)
- https://certification-app.sbsd.virginia.gov/boLogin (vendor-certification sign-in page)
- https://cityofbonitasprings.procureware.com/login (403 Forbidden on the login path itself)
- https://claytonk12ga.bonfirehub.com/login (redirects through account-flows.bonfirehub.com Kratos login flow, terminates 403 Forbidden)
- https://cob.procureware.com/login (403 Forbidden)
- https://contracts-marioncountygcc.msappproxy.net/gateway/Login.aspx (Contract Insight ASP.NET Login.aspx form)
- https://davenport.ionwave.net/Login.aspx (IonWave login form)
- https://dir.my.site.com/BidStamp/VIS_CustomLogin (Salesforce BidStamp vendor login, Visualforce ViewState form)
- https://dmschools.ionwave.net/Vendor/VendorHome.aspx (redirects to Login.aspx)
- https://douglascountypurchasing.ionwave.net/Login.aspx (IonWave login form)
- https://ejbs.fa.us6.oraclecloud.com/supplierPortal/faces/FndOverview?fndGlobalItemNodeId=itemNode_supplier_portal_supplier_portal (Oracle IDCS OAuth/SSO sign-in)
- https://emma.maryland.gov/page.aspx/en/usr/login?ReturnUrl=%2fpage.aspx%2fen%2fbuy%2fhomepage (URL is itself the login page)
- https://esupplier.erp.delaware.gov/psc/fn92pdesup/SUPPLIER/ERP/c/SCP_PUBLIC_MENU_FL.SCP_PUB_REG_CMP_FL.GBL (F5 BIG-IP APM access-denied, errorcode=19)
- https://esupplier.sonomacounty.ca.gov/psc/FN92PRD_9/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL?Page=PT_LANDINGPAGE&Action=H (PeopleSoft sign-in error page)
- https://fayetteville-ar.ionwave.net/Login.aspx (IonWave login wall)
- https://fayetteville-ga.ionwave.net/Login.aspx (IonWave login wall)
- https://financials.ok.gov/psc/SOKLFP1DS/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL? (PeopleSoft sign-in required)
- https://fms-prd.ps.sc.edu/psc/FPRD/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL? (USC CAS Central Authentication Service login page)
- https://fscm.teamworks.georgia.gov/psc/supp/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL? (Team Georgia Marketplace PeopleSoft sign-in required)
- https://gccisd.ionwave.net/ (auto-redirects to Login.aspx)
- https://goodbuy.ionwave.net/Login.aspx (explicit login page)
- https://guest.nasa.gov/ (NASA Guest account login/registration wall)
- https://ha.internationaleprocurement.com/ ("Housing Agency Marketplace" requires Email/Password login)
- https://hamiltoncountyohio.gob2g.com/?TN=hamiltoncountyohio (JS-only login portal shell — Log In/Staff Log In/Register only, "Please enable javascript")
- https://hcpss.bonfirehub.com/login (307 redirect to account.bonfirehub.com central SSO login flow)
- http://norta.procureware.com/login (403 Forbidden on the login path)

### CAPTCHA / bot-check

- https://apps.das.nh.gov/bidscontracts/bids.aspx (HTTP 403 "Access Denied" WAF)
- https://apps.ideal-logic.com/uopcs (JS SPA shell with Cloudflare Turnstile script; no listing content in raw HTML)
- https://bgs.vermont.gov/purchasing (HTTP 403 "ERROR: The request could not be satisfied" — Akamai-style WAF block)
- https://comet-fs.ci.minneapolis.mn.us/psc/supplier/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL?&lp=ERP.SUPPLIER.EP_COSP_PUBLIC_HOME_FL (Cloudflare "Just a moment..." interstitial, HTTP 403)
- https://govwhitepapers.com/?utm_source=GovEvents&utm_medium=NavBar (HTTP 429 "Vercel Security Checkpoint" bot-check, confirmed on retry)
- https://guest.supplier.systems.state.mn.us/psc/fmssupap/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL (redirects to Radware "Captcha Page" at validate.perfdrive.com)
- https://cityofbonitasprings.procureware.com/ (403 Forbidden, likely WAF/bot block — same as its /login path)
- https://dmschools.procureware.com/Companies?t=Info (HTTP 403 Forbidden)

### Dynamic/JS-only content (could not render without a JS-capable browser)

- https://bouldercounty.bonfirehub.com/portal/?tab=openOpportunities (underscore.js client-side template shell, no server-rendered/embedded project JSON)
- https://ccsd.bonfirehub.com/portal/?tab=openOpportunities (same underscore.js template shell pattern)
- https://ci-lubbock-tx.bonfirehub.com/portal/?tab=openOpportunities (same underscore.js template shell pattern, sampled to confirm family)
- https://comalisd.bonfirehub.com/portal/?tab=openOpportunities (Angular SPA shell, ng-app, config JSON only)
- https://cookcountyhealth.bonfirehub.com/portal (same Angular SPA shell pattern)
- https://cookcountyil.bonfirehub.com/portal (same Angular SPA shell pattern)
- https://daviefl.bonfirehub.com/portal (same Angular SPA shell pattern)
- https://dfwairport.bonfirehub.com/portal/?tab=openOpportunities (same Angular SPA shell pattern, no opportunity strings even with tab param)
- https://ecsd.bonfirehub.ca/portal/?tab=openOpportunities (AngularJS SPA shell; only feature-flag JSON and hidden empty-state template)
- https://eprocurement.esmsolutions.com/resetpassword?Token=935c91e0-3b71-4706-88a0-2cc4dc6d5da7 (Angular `<purchase-app>` shell, loading spinner only; password-reset link, not a listing)
- https://fairfaxcounty.bonfirehub.com/portal/?tab=openOpportunities (same Angular SPA shell pattern)
- https://flyri.com/riac/procurement/ ("Active RFPs" table is AJAX-loaded ninja_table plus a React/OpenGov iframe; no listing text in raw HTML)
- https://fortworthtexas.bonfirehub.com/portal/?tab=openOpportunities (same Angular SPA shell pattern)
- https://biddingo.com/soundtransit (Angular SPA shell, `<app-root>`, no server-rendered opportunity content)

Note: the Bonfire (`bonfirehub.com`/`.ca`) platform was assumed server-rendered based on earlier sessions' `?tab=openOpportunities` pages, but this batch found it inconsistent — some instances (bernco, bgca, ggbhtd, habc, homesa — see `easily_scrapable.md`) expose a public JSON API (`/PublicPortal/getOpenPublicOpportunitiesSectionData`) that returns real data even though the initial HTML is a JS template shell, while others tested here returned no accessible data at all through that same approach. Treat each Bonfire subdomain individually rather than assuming platform-wide behavior.

### Broken / error page

- https://apps.nasa.gov/nvdb/vendorSearch (resolves to an unrelated NASA marketing page, not the vendor search tool)
- https://baltimorecounty.prismcompliance.com/ (loads but is only a vendor-registration/compliance hub with no solicitation listing on the page itself)
- http://www.scsk12.org/procurement/bids (raw PHP parse error on `bids.php` line 80)
- https://hacp.org/profile/business-developmentommincorp-com/ (HTTP 404, unrelated WordPress author-archive page)
- https://health.maryland.gov/procumnt/pages/procopps.aspx?utm_source=chatgpt.com (HTTP 404 "File Not Found")

Scope note: this session covered 84 of the 184 remaining unclassified `url_reachable.md` entries (in file order), sorted immediately after each visit rather than in a separate pass, per policy. The other ~100 unclassified reachable URLs remain for a future session.

## 2026-09-29 session 2 (84 URLs from remaining unclassified, Playwright/Chromium; each individually tested)

### Login required

- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=CalState&AuthToken=1%3AAES2%23COeR%2B9y0uJonDteiKZ%2BEXAT%2F0wQEtmCgTPxmtdhiaPctxEQmexjpjCV4N49d5X3drP1zeuVcth%2FPIsK26ub%2FRR7PdwEzslABhuOduB5H9gT3N0M3ug%2FeRnMZKr3z3NgtkQNLRexTFFmXjo%2BndLeXxoucMxlzNwPcEg%3D%3D&SuccessToken=3&URL=ViewSourcingEvent%3FAuthToken%3D1%253AAES2%2523COeR%252B9y0uJonDteiKZ%252BEXAT%252F0wQEtmCgTPxmtdhiaPctxEQmexjpjCV4N49d5X3drP1zeuVcth%252FPIsK26ub%252FRR7PdwEzslABhuOduB5H9gT3N0M3ug%252FeRnMZKr3z3NgtkQNLRexTFFmXjo%252BndLeXxoucMxlzNwPcEg%253D%253D%26CustOrg%3DCalState%26EventId%3D1236956%26SupplierId%3D%26tmstmp%3D1721417133691 (HTTP 200; title: Supplier Login or Join JAGGAER Supplier Network)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=DASIowa&AuthToken=1%3AAES2%23CPmLxE194MfNW61Rm11HoQxaKwxKFaW1exWmJwCj40cAzNj7b2BIxBPkLEOcvTtX%2BpJDJkJ5Cx8If85U3HHktBs0WUA2FhXYx4ylKZlWe6Dl8ZUiNC7QW2%2FpGQ9owC7ixKRB2jAVqLQgkMmXJenZQt6oet7RoJWDSA%3D%3D&SuccessToken=3&URL=ViewSourcingEvent%3FAuthToken%3D1%253AAES2%2523CPmLxE194MfNW61Rm11HoQxaKwxKFaW1exWmJwCj40cAzNj7b2BIxBPkLEOcvTtX%252BpJDJkJ5Cx8If85U3HHktBs0WUA2FhXYx4ylKZlWe6Dl8ZUiNC7QW2%252FpGQ9owC7ixKRB2jAVqLQgkMmXJenZQt6oet7RoJWDSA%253D%253D%26CustOrg%3DDASIowa%26EventId%3D1308705%26SupplierId%3D%26tmstmp%3D1745010830840 (HTTP 200; title: Supplier Login or Join JAGGAER Supplier Network)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=FSU&AuthToken=1%3AAES2%23CB2x1C8s631A6rCRGO4hHp7Pdx5kHuKL5kzpnL4rN84o8fcYVFGer%2BJObLvWJFPDMhE9q7dBcTQFe0kdKrR09eJ4wKnLUwsW8%2FUwf1ksxDTlsRHbnGqPsZBMyH3SybMT5spbptdoYIb9OLTiTlKg%2FDqCHvRcdLpLfA%3D%3D&SuccessToken=3&URL=ViewSourcingEvent%3FAuthToken%3D1%253AAES2%2523CB2x1C8s631A6rCRGO4hHp7Pdx5kHuKL5kzpnL4rN84o8fcYVFGer%252BJObLvWJFPDMhE9q7dBcTQFe0kdKrR09eJ4wKnLUwsW8%252FUwf1ksxDTlsRHbnGqPsZBMyH3SybMT5spbptdoYIb9OLTiTlKg%252FDqCHvRcdLpLfA%253D%253D%26CustOrg%3DFSU%26EventId%3D1336325%26SupplierId%3D%26tmstmp%3D1757094185862 (HTTP 200; title: Supplier Login or Join JAGGAER Supplier Network)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=UConnFullSuite&AuthToken=1%3AAES2%23CHQBTNcjglgXPI2CtvId3j%2BfPuY04WnaPu%2BnsBcMS8bZ215VDuSfTwsRpPtX3iWiCmxfORXDKW1ZbzYtVoPOKlk1OZVSrvaXn6Zj%2FalXbKWUgJXI%2F4ESN2t3wNRSEH%2Fp3h58an4O5hfgusRc8pKjXGdlS7pAYojg2g%3D%3D&SuccessToken=3&URL=ViewSourcingEvent%3FAuthToken%3D1%253AAES2%2523CHQBTNcjglgXPI2CtvId3j%252BfPuY04WnaPu%252BnsBcMS8bZ215VDuSfTwsRpPtX3iWiCmxfORXDKW1ZbzYtVoPOKlk1OZVSrvaXn6Zj%252FalXbKWUgJXI%252F4ESN2t3wNRSEH%252Fp3h58an4O5hfgusRc8pKjXGdlS7pAYojg2g%253D%253D%26CustOrg%3DUConnFullSuite%26EventId%3D1385650%26SupplierId%3D%26tmstmp%3D1777294149216 (HTTP 200; title: Supplier Login or Join JAGGAER Supplier Network)
- https://idm-global.j1p.jaggaer.com/auth/realms/j1p-supplier-idm/login-actions/authenticate?client_id=prod-idp.app.jaggaer.com&tab_id=DvM31H7SmPk (HTTP 400; title: Sign in to Supplier J1 IDM)
- https://hub.edison.tn.gov/psc/fsprd/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL?LP=EP_COSP_PUBLIC_HOME_FL& (HTTP 200; title: Edison Login Page)
- https://idcs-9275a5d3c7c74bb390dab405c8de5456.identity.oraclecloud.com/ui/v1/signin (HTTP 200; title: Cloud Sign In)
- https://lawa.bonfirehub.com/login (HTTP 200; title: Euna Procurement Login Page)
- https://mtc.bonfirehub.com/login (HTTP 200; title: Euna Procurement Login Page)
- https://ntmwd.bonfirehub.com/registration (HTTP 200; title: Euna Procurement Login Page)
- https://scottsdaleaz.bonfirehub.com/login (HTTP 200; title: Euna Procurement Login Page)
- https://login.neighborlysoftware.com/neighborlysoftware.onmicrosoft.com/oauth2/v2.0/authorize?p=b2c_1_signinsignup_prod&client_id=ab730151-4ac5-4b8c-bdd3-4c0f1bffa3a4&response_type=code%20id_token%20token&scope=openid%20email%20profile%20offline_access%20https%3A%2F%2Fneighborlysoftware.onmicrosoft.com%2Fab730151-4ac5-4b8c-bdd3-4c0f1bffa3a4%2FPortal.Read&state=OpenIdConnect.AuthenticationProperties%3DRibwqB29N7HFG%2FlYtBVU9VQQ%2F47hId8udQ7Qgw4gCV5RWxEAhOVi1FNfkygg3UHLQ92Mm5nrr7PtxBGK1Ctu7VQZKAYDWo1Zw0GNewqepMxUgBtdID6wPyRuFfOCGSGsZoucI%2BKrCfxrtk7ZCE%2FsJ6Fer9k%2FkgDMMI%2Bj5ydxbYJsha6Ju%2BbwJkxl2iKxSiWbg7bz%2BzIArwJ%2BKqV8SCsJ5z%2FkyP%2BUts8TiW0nywmKbnDvMxsR8D%2B5A4UNFkxpwjbymbOFiHW9PXRCHqkEhImRWJSDNKMCqIj80loL00VhBpNteMaRXZDaK%2BHEml%2Fw1MkUBLxhoIJQTxiupyJBRNxRhG6dB%2BbWh7CUp1uHipB2lRr8sAjsfh8IPD18auSh31%2Byv71fC0%2FI2e7Kct5SLawcqg%3D%3D&response_mode=form_post&nonce=639174124887079482.NGJmZDQ0N2EtZjkwNi00ZmY4LWI4MWItNmRkMDcwMTQyNTIzMzYyNWQ4MWUtMjExYy00Yjc4LThlMDYtOWJlZDA4YzNhZDdi&tenantCode=waterlooia&portalType=contractor&nTenantId=490&ui_locales=en&machineCode=00000000-0000-0000-0000-000000000000&redirect_uri=https%3A%2F%2Fportal.neighborlysoftware.com%2Floginredirectcomplete&post_logout_redirect_uri=https%3A%2F%2Fportal.neighborlysoftware.com%2Fwaterlooia%2Fcontractor&x-client-SKU=ID_NET472&x-client-ver=7.5.0.0 (HTTP 200; title: Neighborly Software)
- https://marketplace.unisonglobal.com/login.do?resource_name=marketplace (HTTP 200; title: Login)
- https://myncid.nc.gov/index.html (HTTP 200; title: Loading https://myncid.nc.gov/sso)
- https://myncid.nc.gov/index.html#/main/userProfile (HTTP 200; title: Loading https://login.myncid.nc.gov/as/authorizati)
- https://myok-staffing.onconcourse.com/login?type=partner (HTTP 200; title: MyOK Staffing and Services)
- https://ny.newnycontracts.com/FrontPage/VendorMain.asp?XID=4111 (HTTP 200; title: NEW YORK STATE CONTRACT SYSTEM)
- https://oklahoma.gov/omes/divisions/central-purchasing/suppliers-and-payees/supplier-portal.html (HTTP 200; title: Supplier Portal)
- https://onlineservices.osc.state.ny.us/Enrollment/login?17 (HTTP 200; title: New York State Comptroller - Online Services)
- https://passport.cityofnewyork.us/page.aspx/en/buy/homepage/ven (HTTP 200; title: Login: PASSPort)
- https://procurement.opengov.com/login (HTTP 200; title: Login)
- https://procurement.opengov.com/vendors/155272/proposals (HTTP 200; title: Login)
- https://jocogov.ionwave.net/ (HTTP 200; title: Johnson County Bids and Contracts - Login)
- https://jocogov.ionwave.net/Login.aspx (HTTP 200; title: Johnson County Bids and Contracts - Login)
- https://lajoyaisd.ionwave.net/Login.aspx (HTTP 200; title: La Joya ISD e-Bidding Website - Login)
- https://lcpscm.ionwave.net/VendorRegistration/CompanyInfo.aspx (HTTP 200; title: Supplier Registration)
- https://leegov.ionwave.net/Login.aspx (HTTP 200; title: Lee County Bids & Contracts - Login)
- https://lexingtoncounty.ionwave.net/Vendor/VendorHome.aspx (HTTP 200; title: Lexington E-Procurement - Login)
- https://lexingtonky.ionwave.net/Login.aspx (HTTP 200; title: Lexington-Fayette Urban County Government - Login)
- https://lrsd.ionwave.net/Login.aspx (HTTP 200; title: Little Rock School District - Login)
- https://miamiu-ohiousourcing.ionwave.net/Login.aspx (HTTP 200; title: Miami U & Ohio U Sourcing - Login)
- https://nevada.ionwave.net/ (HTTP 200; title: Nevada Gov eMarketplace - Login)
- https://sawsbid.ionwave.net/Login.aspx (HTTP 200; title: SAWS Purchasing Department - Login)
- https://kbrsupplier.com/default.aspx (HTTP 200; title: KBRSupplier)

### Cloudflare / WAF / 403 block

- https://hosting.portseattle.org/sops/ (HTTP 403; title: Just a moment...)
- https://hosting.portseattle.org/sops/#/Dashboard (HTTP 403; title: Just a moment...)
- https://identity.planetbids.com/identity/public/client/login.html?appCode=portal&agency_id=20134&client_id=connected-app-live-a6ef820a-76d1-4cab-9e2c-26e9f246cf8f&redirect_uri=https%3A%2F%2Fvendors.planetbids.com%2Foauth%2Fcallback&state=%7B%22agency_id%22%3A20134%7D&agency_name=North+County+Transit+District&organizationId=organization-live-4b1a8e07-9503-4b5c-8dea-4e537ec156ff&enableOtpLogin=true&showOtpPrompt=false&registerUrl=https%3A%2F%2Fvendors.planetbids.com%2Fportal%2F20134%2Fvp%2Fvp-prereg&forgotPasswordUrl=https%3A%2F%2Fvendors.planetbids.com%2Fportal%2F20134%2Freset-password (HTTP 403; title: 403 Forbidden)
- https://identity.planetbids.com/identity/public/client/login.html?appCode=portal&agency_id=53010&client_id=connected-app-live-a6ef820a-76d1-4cab-9e2c-26e9f246cf8f&redirect_uri=https%3A%2F%2Fvendors.planetbids.com%2Foauth%2Fcallback&state=%7B%22agency_id%22%3A53010%7D&agency_name=Long+Beach+City+College&organizationId=organization-live-4b1a8e07-9503-4b5c-8dea-4e537ec156ff&enableOtpLogin=true&showOtpPrompt=false&registerUrl=https%3A%2F%2Fvendors.planetbids.com%2Fportal%2F53010%2Fvp%2Fvp-prereg&forgotPasswordUrl=https%3A%2F%2Fvendors.planetbids.com%2Fportal%2F53010%2Freset-password (HTTP 403; title: 403 Forbidden)
- https://identity.planetbids.com/identity/public/client/login.html?appCode=portal&agency_id=73214&client_id=connected-app-live-a6ef820a-76d1-4cab-9e2c-26e9f246cf8f&redirect_uri=https%3A%2F%2Fvendors.planetbids.com%2Foauth%2Fcallback&state=%7B%22agency_id%22%3A73214%7D&agency_name=Sacramento+Municipal+Utility+District&agency_logo=https%3A%2F%2Ffiles-prod01.planetbids.com%2Ff73214%2F20250428114636755+SMUD_Logo_4c.png&organizationId=organization-live-4b1a8e07-9503-4b5c-8dea-4e537ec156ff&enableOtpLogin=true&showOtpPrompt=false&registerUrl=https%3A%2F%2Fvendors.planetbids.com%2Fportal%2F73214%2Fvp%2Fvp-prereg&forgotPasswordUrl=https%3A%2F%2Fvendors.planetbids.com%2Fportal%2F73214%2Freset-password (HTTP 403; title: 403 Forbidden)
- https://identity.planetbids.com/identity/public/oauth/login?appCode=portal&agency_id=39471&client_id=connected-app-live-a6ef820a-76d1-4cab-9e2c-26e9f246cf8f&redirect_uri=https%3A%2F%2Fvendors.planetbids.com%2Foauth%2Fcallback&state=%7B%22agency_id%22%3A39471%7D&agency_name=San%20Diego%20Housing%20Commission (HTTP 403; title: 403 Forbidden)
- https://identity.planetbids.com/identity/public/oauth/login?appCode=portal&agency_id=41576&client_id=connected-app-live-a6ef820a-76d1-4cab-9e2c-26e9f246cf8f&redirect_uri=https%3A%2F%2Fvendors.planetbids.com%2Foauth%2Fcallback&state=%7B%22agency_id%22%3A41576%7D&agency_name=City%20of%20Menifee (HTTP 403; title: 403 Forbidden)
- https://lakeworthbeachfl.bidsandtenders.net/Module/Tenders/en/Home/BidsHomepage (HTTP 403; title: )
- https://login.ehawaii.gov/lala (HTTP 403; title: 403 Forbidden)
- https://madisonal.procureware.com/login (HTTP 403; title: 403 Forbidden)
- https://mdapex.ecenterdirect.com/ (HTTP 403; title: 403 Forbidden)
- https://pro.prismcompliance.com/ (HTTP 403; title: 403 Forbidden)
- https://pro.prismcompliance.com/default.aspx (HTTP 403; title: 403 Forbidden)
- https://proportal.sourcewell-mn.gov/Module/Tenders/en/Vendor/Dashboard/b50f7d44-0fe6-4ffe-8621-fbae66354482 (HTTP 403; title: )
- https://procure.cgieva.com/page.aspx/en/sup/registration_extranet/save (HTTP 200; title: Browser check: Virginia)

### Broken / error page

- https://iris-vss.alaska.gov/ (HTTP 500; title: The URL you requested has been blocked)
- https://lagoverpvendor.doa.louisiana.gov/irj/portal (HTTP 502; title: )
- https://login-euxp-saasfaprod1.fa.ocs.oraclecloud.com/oam/server/obrareq.cgi?ECID-Context=1.0062xRLviAgFS8V5u30FyX0007aI0003xm%3BkXjE (HTTP 503; title: Service Unavailable)
- https://login-exkk-saasfaprod1.fa.ocs.oraclecloud.com/oam/server/obrareq.cgi?encquery%3D5KbKcxXM%2Fj31a5DXL88CkKQxNL8xTgjx4o0T1qvnZ%2Fm8L2PVioR3VV1mC34DycQZg0dWLUr3o1012giKiZTeLaHBd98AahIgscHY6X%2BjknHWJTGvHe2M7sMJAhATajCClH2Gx0nkCL6bzAbl%2BeHZ6uiXgB%2B2hOmd%2FQzizf5Y4YNkakpfRK5yMBTn8PZ9OsPNGrM%2B9IEZeXceK4jlLN54auwgY6%2B6KY4M7NGvbtyUVhrexBSDMkJ1OjzgiQG26s7nUNgDOOBUY1V47R2%2FWeMq%2Bd5RS64LygmWx1uZVUYM2hKWN3EGASc%2FSKuhZmDEEqqbRerUTv8simlP4wr9hR9Mpg0V0hRCebgR0PJpg4%2BHF7Ag3SZ7q9E7%2BHfRzp%2F3W%2B3GmJQk%2BTkTLecO55P653z0xHK1qj1hCGfUC%2F7kmkzXjp1zFdxcYxy0Wmms4vL3XeoVshFxno55Xarw4aCIFXtNTxZWRW7uf5m0Zw2p6WcH89Wrs2vxPwt6PMezO3rioKyymXYA0SEkvDg3C%2FapCuEENBINGbNbfVXmU9HJ3r8XnlclYMyGyIGLAznYm98%2BiO%2F0AWsh3bbiaxSI9qt8veZReDf6Rn9T76JBWjcttWwXXZET%2BU4t5KxKqJ1QJxPAEhmZzJZ2sRAm4bRXVI4ODGQRpEciLt8Lj3lB9rFv9tqgF10%3D%20agentid%3DOraFusionApp_11AG%20ver%3D1%20crmethod%3D2%26cksum%3D75ca2eec8e5ee3dbd0b2a672207ad24ecf7dc56a&ECID-Context=1.006Ivf_oUN8AxGKayTaeMG0060Ok0001FM%3BkXjE (HTTP 503; title: Service Unavailable)
- https://login-ibqhjb.fa.ocs.oraclecloud.com/oam/server/obrareq.cgi?encquery%3DxS138OL6YUFqo5kXqhatUBRr5X3V1RGL4k%2Bz0kVeSsDqPlMtLQOkCPPbjyD9zFAHBZaV%2B4%2Bm1%2BC15RRXqDUzJfqgkiyvt3ZB8iYpaRVN9qApx0UAl6kxqVcVIFnLXt9LuTk4KALc3n4SIQddr6q6%2BOFzVzgiKyWa3cqoE2V12YBzK8Pi2SYryl1afztYU9JVUJP29U%2FlKJqV7biRJbQE9H2sPdqJv3kpoyqbSpybx21q5XYhaPoGc2tLTa6xi%2FRfih66LyuMO4FMp8vH5zA12aZ9ltzcyzAVFI3x7uQLcAh6pHQm7VqoYEwfyhjgh7FaYQ9cE67Q%2BeRAkhh0r5dlkA%2Fjbd93rdrtDAMuzNqFGgeGYMM%2F3wqSyRTAXhDr9kp1RGsdNmsK1lr6FA9OZ2brJTDDbjPwVNPLMB3TyYleKacbH9%2FXviCjUQ%2FHwzgt5a9ZuBGEumvbK0TxwMpgsJ0yu0jXJ6%2BfZNKN5%2FaG4Pxi2jY47gyzltsiogFvef6dIlZzVXVFjPIDgDWoc%2BR0v7%2BtJDZbAdRc3bNMWuWNuFlHz2%2BemlSYNUCtIqoSCOFJ3PMxgHpdIwsCoLnHZ1A0BPrjrnmeJlZ1BLCj1XMN8aCDPaJXMm8GUoFpBDoJcVgnroYkpEYrk4FICQDlSWQJyHDEZvAyf8mrlleFvHliIKe7iqCM0VrJPJxOx3XLM4%2FFoSIgzv34BqFfX4c4fRTLYbEEbRj5%2FXmyMe04mzMmfdsm1rdZs7boBYCvTXKmhklZQme33TFM26PGec1T0ZnFkODoiPWb3%2FSouG2DGmvCBo7uh0cfmdMNlRngKQDEg9Gi8IlTDr5a4zrqqOzUe5eYoFAwMHRnZ%2Bi9XY%2B%2FbqXxXqBVLWnW6hwImdtNFjXGJuER7GbvbnYWaahNTQQ5aBDezpKFOUdrjSKzI6ICdCnXnnpPo%2BgKo9HQXsMrFc89CE%2BnPbXiforjn%2FjUa7sPlnIN3occRYXNafpmYekQzHYI%2F5J1L1TsBHOdebeWGx20HeLYJXFOWGup58ViARCFzp0cgp8GZntiBKsdecvdg97v5k3sO5HEWS96IYcQHlDmXIdsdBsPOG1cvSJ1JixuseaaZM5OMnOTxpsV1uToblun5Vs6DfOgTv3VUQXVevMFCyC%2BTBucOnTiZCfdT92T%2Bp1XkdveKsJ2jeRebG165AKqLnEJ5eZQhBs6eWn9v%2FRow0mdfeKFavO7Fr%2FXELn9GXe13oQh0sy0RX4kW1qvKVWgI9%2FfiVQMikBsESPOFMA5dwtAFr%2BggEb7aYvdjXYs6zvmlxNxNyXwN2m3GcH7mf%2FopLRrFKVdnqD00kjja5i%2FNebYOfMTMGLVHIoL5EorazZ1hyrc2bafEjj63su3Ns2ltD0kTZvQpgdySfeQEZ21WjibhABsOHZ9SPQE91Ss5TAF6LYkOztU1VyaPmp5g%2BEwbirV3o%2FDo9a%2Fi%2By%2BFvDpPWBkpt2bIHXxWj%2F3699%2BniBsU97TRPn3nRmAmTie6HCRb0kH4k1oTrl70mjMjsI8O3bhdvhj1EnFU8r6ZSszcyTneTE%2Bma7MCYbylmnwQppds6nbIQFyzq4UMv1nLeAS3MHFZkThUexNB165wz0ycXAKMEqID%2FiVHZok2XfhRFfcA2bIk7Y%2FiBD1CplaGU%2F30%2FTC0u61H3iD5Hulp7L5f7jBTp5IjQ%3D%3D%20agentid%3DOraFusionApp_11AG%20ver%3D1%20crmethod%3D2%26cksum%3Db7d14dfa13cdabd935ca9c7841fb201bfe34a229&ECID-Context=1.006Ji0n6W6n2FSMqyKvX6G003mVL0000wW%3BkXjE (HTTP 503; title: Service Unavailable)
- https://mecknc-vss.hostams.com/PRDVSS1X1/Advantage4 (HTTP 500; title: The URL you requested has been blocked)
- https://octa.govqa.us/WEBAPP/_rs/(S(hn5r0labmmsdycjs2dfu2bmf))/SupportHome.aspx?sSessionID=136023057:64058TERBOPBL%5BFZ%5BSWSTLWXOUBTSH (HTTP 200; title: Page Temporarily Unavailable)
- https://onesource.wsscwater.com//OA_HTML/RF.jsp?function_id=1016386&resp_id=-1&resp_appl_id=-1&security_group_id=0&lang_code=US&params=PhlO--YbzhGGoNoQiWelCZh8E6l6Vyf-l4j.nKjuI12HTsr8tTeQfKj07gHqCs2V0m07ZPkHnatj9d0m7aE2QQ&oas=hqMw_v58KSRcN5hDt1ZHUg (HTTP 200; title: Error)
- https://onesource.wsscwater.com/OA_HTML/RF.jsp?function_id=1016386&resp_id=-1&resp_appl_id=-1&security_group_id=0&lang_code=US&params=PhlO--YbzhGGoNoQiWelCZh8E6l6Vyf-l4j.nKjuI12HTsr8tTeQfKj07gHqCs2V0m07ZPkHnatj9d0m7aE2QQ&oas=hqMw_v58KSRcN5hDt1ZHUg (HTTP 200; title: Error)

### Uncertain (loads but listing not confirmed public / JS-rendered blank)

- https://knoxbuys.buyspeed.com/bso/view/login/login.xhtml (HTTP 200; title: Knox County Procurement - /view/login/login.xhtml)
- https://longbeachbuys.buyspeed.com/bso/view/login/login.xhtml (HTTP 200; title: Long Beach Buys - /view/login/login.xhtml)
- https://oregonbuys.gov/bso/view/login/login.xhtml (HTTP 200; title: OregonBuys - /view/login/login.xhtml)
- https://procure.portlandoregon.gov/bso/seller/bidAck.sdo (HTTP 200; title: City of Portland | BuySpeed - /view/login/login.xh)
- https://lacounty.gov/business/doing-business-with-la-county/lac-purchasing-and-contract-opportunities/ (HTTP 200; title: LA County Purchasing and Contract Opportunities – )
- https://mwrd.app/Cntrctann/ (HTTP 200; title: Contract Announcements)
- https://pasupplierportal.state.pa.us/irj/portal/anonymous (HTTP 200; title: PA Supplier Portal Home - SAP NetWeaver Portal)
- https://pbcvssp.co.palm-beach.fl.us/webapp/vssp/AltSelfService?EmailToken=02730029218941640788 (HTTP 200; title: VSSPRD - Welcome to Palm Beach County’s Vendor Sel)
- https://mevss.hostams.com/PRDVSS1X1/AltSelfService (HTTP 200; title: Welcome to CGI Advantage Vendor Self Service Porta)
- https://pbsystem.planetbids.com/portal/13821/portal-home (HTTP 200; title: PlanetBids Vendor Portal)
- https://pbsystem.planetbids.com/portal/13982/login (HTTP 200; title: PlanetBids Vendor Portal)
- https://pbsystem.planetbids.com/portal/13982/login# (HTTP 200; title: PlanetBids Vendor Portal)
- https://pr-webs-vendor.des.wa.gov/ (HTTP 200; title: WEBS)
- https://my.alaska.gov/adfs/ls/?wa=wsignin1.0&wtrealm=https%3a%2f%2fmy.alaska.gov%2f&wctx=rm%3d0%26id%3dpassive%26ru%3d%252fPortal%252fPortal.aspx&wct=2023-11-24T17%3a55%3a54Z (HTTP 403; title: alaska.gov)

Note: the Bonfire detail pages (e.g. `mps.bonfirehub.com/opportunities/*`) are behind a Cloudflare check even though listing grids load; IonWave "Current Bids" links were not opened this pass.
