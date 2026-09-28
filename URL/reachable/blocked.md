# Blocked (Reachable subset)

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
