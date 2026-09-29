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

## 2026-09-29 session (84 URL batch: unclassified rows 1-84)

### Login required

- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=CalState&AuthToken=1%3AAES2%23COeR%2B9y0uJonDteiKZ%2BEXAT%2F0wQEtmCgTPxmtdhiaPctxEQmexjpjCV4N49d5X3drP1zeuVcth%2FPIsK26ub%2FRR7PdwEzslABhuOduB5H9gT3N0M3ug%2FeRnMZKr3z3NgtkQNLRexTFFmXjo%2BndLeXxoucMxlzNwPcEg%3D%3D&SuccessToken=3&URL=ViewSourcingEvent%3FAuthToken%3D1%253AAES2%2523COeR%252B9y0uJonDteiKZ%252BEXAT%252F0wQEtmCgTPxmtdhiaPctxEQmexjpjCV4N49d5X3drP1zeuVcth%252FPIsK26ub%252FRR7PdwEzslABhuOduB5H9gT3N0M3ug%252FeRnMZKr3z3NgtkQNLRexTFFmXjo%252BndLeXxoucMxlzNwPcEg%253D%253D%26CustOrg%3DCalState%26EventId%3D1236956%26SupplierId%3D%26tmstmp%3D1721417133691 - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=DASIowa&AuthToken=1%3AAES2%23CPmLxE194MfNW61Rm11HoQxaKwxKFaW1exWmJwCj40cAzNj7b2BIxBPkLEOcvTtX%2BpJDJkJ5Cx8If85U3HHktBs0WUA2FhXYx4ylKZlWe6Dl8ZUiNC7QW2%2FpGQ9owC7ixKRB2jAVqLQgkMmXJenZQt6oet7RoJWDSA%3D%3D&SuccessToken=3&URL=ViewSourcingEvent%3FAuthToken%3D1%253AAES2%2523CPmLxE194MfNW61Rm11HoQxaKwxKFaW1exWmJwCj40cAzNj7b2BIxBPkLEOcvTtX%252BpJDJkJ5Cx8If85U3HHktBs0WUA2FhXYx4ylKZlWe6Dl8ZUiNC7QW2%252FpGQ9owC7ixKRB2jAVqLQgkMmXJenZQt6oet7RoJWDSA%253D%253D%26CustOrg%3DDASIowa%26EventId%3D1308705%26SupplierId%3D%26tmstmp%3D1745010830840 - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=FSU&AuthToken=1%3AAES2%23CB2x1C8s631A6rCRGO4hHp7Pdx5kHuKL5kzpnL4rN84o8fcYVFGer%2BJObLvWJFPDMhE9q7dBcTQFe0kdKrR09eJ4wKnLUwsW8%2FUwf1ksxDTlsRHbnGqPsZBMyH3SybMT5spbptdoYIb9OLTiTlKg%2FDqCHvRcdLpLfA%3D%3D&SuccessToken=3&URL=ViewSourcingEvent%3FAuthToken%3D1%253AAES2%2523CB2x1C8s631A6rCRGO4hHp7Pdx5kHuKL5kzpnL4rN84o8fcYVFGer%252BJObLvWJFPDMhE9q7dBcTQFe0kdKrR09eJ4wKnLUwsW8%252FUwf1ksxDTlsRHbnGqPsZBMyH3SybMT5spbptdoYIb9OLTiTlKg%252FDqCHvRcdLpLfA%253D%253D%26CustOrg%3DFSU%26EventId%3D1336325%26SupplierId%3D%26tmstmp%3D1757094185862 - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=MDAndersonPS - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=StateOfNewMexico - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=TAMU - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=TriC - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=UConnFullSuite&AuthToken=1%3AAES2%23CHQBTNcjglgXPI2CtvId3j%2BfPuY04WnaPu%2BnsBcMS8bZ215VDuSfTwsRpPtX3iWiCmxfORXDKW1ZbzYtVoPOKlk1OZVSrvaXn6Zj%2FalXbKWUgJXI%2F4ESN2t3wNRSEH%2Fp3h58an4O5hfgusRc8pKjXGdlS7pAYojg2g%3D%3D&SuccessToken=3&URL=ViewSourcingEvent%3FAuthToken%3D1%253AAES2%2523CHQBTNcjglgXPI2CtvId3j%252BfPuY04WnaPu%252BnsBcMS8bZ215VDuSfTwsRpPtX3iWiCmxfORXDKW1ZbzYtVoPOKlk1OZVSrvaXn6Zj%252FalXbKWUgJXI%252F4ESN2t3wNRSEH%252Fp3h58an4O5hfgusRc8pKjXGdlS7pAYojg2g%253D%253D%26CustOrg%3DUConnFullSuite%26EventId%3D1385650%26SupplierId%3D%26tmstmp%3D1777294149216 - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=UIdaho - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- https://app01.jaggaer.com/apps/Router/SupplierLogin?CustOrg=URI - JAGGAER supplier login (AggieBid sample confirmed no listing without login; rest of family not individually tested)
- http://newhavenhousing.cobblestonesystems.com/gateway/Login.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://baltimorecity.diversitycompliance.com/FrontPage/VendorMain.asp?XID=2708 - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://baltimorecounty.prismcompliance.com/ - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://bids.wyomingmi.gov/Bid/SpecDownload/2236?fromLogin=1 - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://brazosbid.ionwave.net/Login.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://certification-app.sbsd.virginia.gov/boLogin - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://claytonk12ga.bonfirehub.com/login - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://comet-fs.ci.minneapolis.mn.us/psc/supplier/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL?&lp=ERP.SUPPLIER.EP_COSP_PUBLIC_HOME_FL - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://contracts-marioncountygcc.msappproxy.net/gateway/Login.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://davenport.ionwave.net/Login.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://dir.my.site.com/BidStamp/VIS_CustomLogin - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://dmschools.ionwave.net/Vendor/VendorHome.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://douglascountypurchasing.ionwave.net/Login.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://ejbs.fa.us6.oraclecloud.com/supplierPortal/faces/FndOverview?fndGlobalItemNodeId=itemNode_supplier_portal_supplier_portal - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://emma.maryland.gov/page.aspx/en/usr/login?ReturnUrl=%2fpage.aspx%2fen%2fbuy%2fhomepage - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://eprocurement.esmsolutions.com/resetpassword?Token=935c91e0-3b71-4706-88a0-2cc4dc6d5da7 - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://esupplier.sonomacounty.ca.gov/psc/FN92PRD_9/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL?Page=PT_LANDINGPAGE&Action=H - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://fayetteville-ar.ionwave.net/Login.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://fayetteville-ga.ionwave.net/Login.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://financials.ok.gov/psc/SOKLFP1DS/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL? - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://fms-prd.ps.sc.edu/psc/FPRD/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL? - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://fscm.teamworks.georgia.gov/psc/supp/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL? - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://gccisd.ionwave.net/ - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://goodbuy.ionwave.net/Login.aspx - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://guest.supplier.systems.state.mn.us/psc/fmssupap/SUPPLIER/ERP/c/NUI_FRAMEWORK.PT_LANDINGPAGE.GBL - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://ha.internationaleprocurement.com/ - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://hamiltoncountyohio.gob2g.com/?TN=hamiltoncountyohio - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)
- https://hcpss.bonfirehub.com/login - login page / no public list seen (IonWave sample brazosbid confirmed; PeopleSoft sample Oklahoma; family not individually tested)

### Cloudflare / WAF blocked

- http://norta.procureware.com/login - 403 Forbidden
- https://cityofbonitasprings.procureware.com/ - 403 Forbidden
- https://cityofbonitasprings.procureware.com/login - 403 Forbidden
- https://cob.procureware.com/login - 403 Forbidden
- https://dmschools.procureware.com/Companies?t=Info - 403 Forbidden
- https://apps.das.nh.gov/bidscontracts/bids.aspx - 403 / request blocked
- https://bgs.vermont.gov/purchasing - 403 / request blocked
- https://bidportal.ksu.edu/Module/Tenders/en/Vendor/Dashboard/70f4d5cf-dabf-47c6-a618-3522733a7088 - 403 / request blocked

### CAPTCHA / bot-check

- https://govwhitepapers.com/?utm_source=GovEvents&utm_medium=NavBar - Vercel security checkpoint (429)

### Broken / error pages

- http://www.scsk12.org/procurement/bids - PHP parse error / 404 / 503
- https://hacp.org/profile/business-developmentommincorp-com/ - PHP parse error / 404 / 503
- https://health.maryland.gov/procumnt/pages/procopps.aspx?utm_source=chatgpt.com - PHP parse error / 404 / 503

### Uncertain

- https://apps.ideal-logic.com/uopcs - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://bernco.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://bgca.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://biddingo.com/soundtransit - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://bidlocker.us/Home/bidlockerus - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://bouldercounty.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://ccsd.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://ci-lubbock-tx.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://comalisd.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://cookcountyhealth.bonfirehub.com/portal - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://cookcountyil.bonfirehub.com/portal - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://daviefl.bonfirehub.com/portal - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://dfwairport.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://ecsd.bonfirehub.ca/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://esupplier.erp.delaware.gov/psc/fn92pdesup/SUPPLIER/ERP/c/SCP_PUBLIC_MENU_FL.SCP_PUB_REG_CMP_FL.GBL - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://fairfaxcounty.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://fortworthtexas.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://ggbhtd.bonfirehub.com/portal/ - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://habc.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
- https://homesa.bonfirehub.com/portal/?tab=openOpportunities - listing did not render in this run (JS-rendered Bonfire/Biddingo/BidLocker/etc. or connection timeout); sample cookcountyil/fairfax showed only spinners
