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
