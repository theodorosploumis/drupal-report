# Drupal fixes & changes Report, RFP tips

> How to estimate the costs and time needed to fix issues or make changes to a Drupal website that you did not develop!
> Before giving a proposal (RFP) you need to inspect the site! But inspecting a Drupal site is not as simple as you believe...
> Here is a **basic checklist** of the Report that you need to deliver before doing anything on the site.

See and **example of a report on [example-report.md](https://github.com/theodorosploumis/drupal-report/blob/master/example-report.md).

### Before the Report needs
- [ ] **Technical specification document** (if exists).
- [ ] Current **Process flow diagram** (in case the system communicates with other services)
- [ ] **Drupal admin credentials** (user 1, or Admin role account). This is needed to check the existing structure, functionality, modules etc. Normally there whould be a dev subdomain to log in. If not credentials and demo provided ask for the git code and a dumb database to install the project locally.
- [ ] A **brief of the project scope**.
- [ ] What are the **project goals** (eg register new members)? How do they measure them? Do they currently meet the goals?
- [ ] What happened with the previous Developer/Company (and there is no collaboration anymore)?
- [ ] **Why the site needs the changes** (fixes, update, upgrate, migration etc)?
- [ ] **How much time needed to build the project?**
- [ ] Will there be a **new Skin** (or theme, template whatever they call it)?
- [ ] What are the **things that do not work well** now and they would like to improve?
- [ ] How many **different Authors** are currently adding content?
- [ ] How many **different User Roles** exist (eg Anonymous, Member, Pro Member etc)? Which are each Role permissions on the project? Can we simplify any process for the users?
- [ ] **How many Drupal nodes** (you can name it as "pages") are currently on the database?
- [ ] Will we need a **data migration**? If so, are there any content entry fields we need to remove or any new we need to add?
- [ ] Are there any (high) **payments to 3rd party services** that we can avoid? Eg a CDN.
- [ ] Who is going to **support the project** technically (Drupal updates, security issues, technical support)? Remember to provide a yearly Support subscription with specific tasks on the contract.
- [ ] **Where is the project hosted** now? What are the needs for Database, PHP etc? Are there any special software used? Offer to move to a new hosting provider if current does not fit us. For big customers offer Drupal cloud based solutions (Acquia, Pantheon etc).

Other (not so important but could be important)
- [ ] Hosting credentials (to check server/system details, tools installed etc that are special for the project to work).
- [ ] Other services credentials (eg CDN, SSL provider, Google Analytics etc) that are used.

### Common Reports
- [ ] Site performance (use well known services such as [PageSpeed](https://developers.google.com/speed/pagespeed/insights), [gtmetrix](https://gtmetrix.com) and [yellowlab.tools](https://yellowlab.tools))
- [ ] SEO (Does the project follow the basic SEO rules?)
- [ ] Mobile UX and design (does it work well on small screens?)
- [ ] Heatmap reports (eg using tools like [Hotjar](https://www.hotjar.com))
- [ ] Security issues reports (eg using [hackertarget.com/drupal-security-scan](https://hackertarget.com/drupal-security-scan/), [securityheaders.com](https://securityheaders.com/), [sitecheck.sucuri.net](https://sitecheck.sucuri.net/))

### Drupal specific Reports
- [ ] Drupal content Structure (Content types, taxonomy etc)
- [ ] What is the main functionality (Features and Functionality, F&F) provided (eg login, register, add comments, share content etc)
- [ ] Drupal forms
- [ ] How many different pages are there
- [ ] Is there a mobile verison of the website or responsive css styles
- [ ] Usage of special modules (eg Panels, Features, Context, Paragraphs, php etc)
- [ ] Drupal user Roles
- [ ] Create 1 demo user for each Drupal Role and get into the site to inspect functionality (take screenshots, investigate bad UX etc). Alternatively you can use [masquerade](https://www.drupal.org/project/masquerade) to become another user)
- [ ] Drupal best practices
- [ ] Theming (uses ds, template files, preprocess functions, field layout, panels, patternlab etc)
- [ ] Total modules enabled
- [ ] Modules that should not be used
- [ ] Modules that should be used
- [ ] (Security) Updates
- [ ] Views best practices
- [ ] Menus and navigation
- [ ] Text filters and editors
- [ ] Block types and block structure
- [ ] Multilingual behavior
- [ ] PHP and server settings (eg using a high php memory limit, not protected settings file etc)

### What to deliver
- [ ] A **pdf** of the report (use Google Docs to create the official report)
- [ ] Include images/screenshots when needed to explain the text
- [ ] **Propose changes** with details for every aspect that need to change
- [ ] **Include prices and timesheet** for every change mentioned
- [ ] An **invoice of 10hr - 100hr working** (the working hours depend on the size of the site)

Example [report here](example-report.md).

### Useful Drupal modules
- [forena (7.x, 8.x)](https://www.drupal.org/project/forena)
- [site_audit (7.x, 8.x)](https://www.drupal.org/project/site_audit)
- [security_review (7.x, 8.x)](https://www.drupal.org/project/security_review)
- [seckit (7.x, 8.x)](https://www.drupal.org/project/seckit)
- [seo_checklist (7.x, 8.x)](https://www.drupal.org/project/seo_checklist)
- [prod_check (7.x, 8.x)](https://www.drupal.org/project/prod_check)
- [systeminfo (7.x)](https://www.drupal.org/project/systeminfo)
- [field_report (8.x)](https://www.drupal.org/project/field_report)
- [entity_reports (8.x)](https://www.drupal.org/project/entity_reports)
- [site_complexity (8.x)](https://www.drupal.org/project/site_complexity)
- [documentation_export (8.x)](https://www.drupal.org/project/documentation_export)
- [content_report (7.x)](https://www.drupal.org/project/content_report)
- [plugin (8.x)](https://www.drupal.org/project/plugin)
- [entity_relationship (8.x)](https://github.com/skilld-labs/entity_relationship)
- [erd (7.x, 8.x)](https://www.drupal.org/project/erd)
- [dependency_visualizer (8.x)](https://www.drupal.org/project/dependency_visualizer)
- [entity_dependency_visualizer (8x)](https://www.drupal.org/project/entity_dependency_visualizer)
- [quant (7.x)](https://www.drupal.org/project/quant)
- [panels_pane_report (7.x)](https://www.drupal.org/project/panels_pane_report)
- [upgrade_check (6.x, 7.x)](https://www.drupal.org/project/upgrade_check)
- [mglaman/drupal-check](https://github.com/mglaman/drupal-check)
- [d8_migration_check (7.x)](https://www.drupal.org/project/d8_migration_check)

### Drupal Console commands

https://drupalconsole.com/docs/en/commands

- drupal field:info
- drupal debug:\*

### Scripts to generate software report

- https://github.com/theodorosploumis/generate_drupal_report

### My thoughts
- Avoid giving an estimate/proposal before making a site Report.
- Do not start the Report before getting the credentials or a demo.
- Try to find out what does the website mean for the owner (eg if it is the main income source).
- If able propose to fix one thing at a time using agile methodology and get paid by the hour.
- Tell your customer that this Report is like a Doctor diagnosis and that it can be used for future tasks.
- Do not forget to include costs such as for copying the site/db, creating a dev environment, uploading changes to live environment (eg usage of features module) etc.
- After the Report, avoid touching projects that are not well structured and do not follow (Drupal) best practices!
- Avoid expressing negative for other Companies/Developers (talk about the site and not about the people that were involved).
- Such projects are good to "learn" new things and other people practices (educational projects).

### Useful resources
- [Drupal Audit Guide](https://github.com/axelerant/engineering/blob/main/audit.md)
- [Slide, Auditing Drupal Sites](https://www.slideshare.net/exove/auditing-drupal-sites)
- [The Gizra way pricing method](https://gist.github.com/theodorosploumis/826412bb5f2dd0aadf2728f950ffa225)
- [Palantir Build Spec 1.0 - Google Sheets](https://docs.google.com/spreadsheets/d/15htLLWLguhwiuTLg_nndQNpgWVdUMy6UaR_d1q-v6iw/edit#gid=0)
- [Drupal Early Estimation Sheet Template (version 3, Feb 2011) - Google Sheets](https://docs.google.com/spreadsheets/d/13MGHIxFOtbJ2Qxygc_GxKzxqghLiK1-7YgNiq95ypWE/edit?hl=en#gid=0)
- [Drupal Spec Tool v2.0.0 (current) - Google Sheets](https://docs.google.com/spreadsheets/d/1h-SieCV9Dtrj8F4bqMvsbcHwIibN30j2oR9FMRDFT-8/edit#gid=0)
- [Drupal Estimation Techniques by Project Managers](https://www.slideshare.net/jakobpersson/drupal-estimation-techniques-by-project-managers)
- [D8 Upgradation Estimate](http://migrate.opensenselabs.com/migration-report/techtud)
- [Drupal fixed budget projects : the art of estimates](https://www.slideshare.net/MaximeTopolov/drupal-fixed-budget-projets-the-art-of-estimates)
- [How Big, How Long, How Much: Estimating Drupal Project Size, Duration, and Cost - YouTube](https://www.youtube.com/watch?v=cIrdqyw0tvc)
- [How we estimate our Drupal web development projects — Internetdevels](https://internetdevels.com/blog/how-we-estimate-drupal-web-development-projects)
- [Estimating Drupal Projects | Metal Toad](https://www.metaltoad.com/blog/estimating-drupal-projects)
- [Are we afraid to estimate our work in Drupal and open source? - Drupal Webform Estimation Open Source](https://www.jrockowitz.com/blog/estimation)
- [How We Estimate Drupal Projects - Codesushi. Web & Application Solutions](https://codesushi.co/codesushi/estimate-drupal-projects/)
- [10 problems with Web Development Projects and how we've solved them](https://www.freelock.com/newsletter/10-problems-web-development-projects-and-how-weve-solved-them)
- [Video, DrupalCon New Orleans 2016: Let's be honest: Estimation is guessing](https://www.youtube.com/watch?v=rcYYOquSk-Y)
- [Video, DrupalCon Vienna 2017: Estimates are dead, long live forecasting!](https://www.youtube.com/watch?v=_pxWPGYRLDA)
- [Video, DrupalCon Denver 2012: NO RFPS! WHY REQUESTS FOR PROPOSALS ARE BAD FOR BUSINESS](https://www.youtube.com/watch?v=25ii8fNisP4)
- [Video, Bay Area Drupal Camp 2015: How to do a Site Audit](https://www.youtube.com/watch?v=ZLTlJ_6aYGQ)
- [Video, DrupalCon New Orleans 2016: How to audit Drupal Sites for performance, content and best practices](https://www.youtube.com/watch?v=A0XCRETqfYk)
- [Video, How to audit Drupal Sites for performance, content and best practices, 2016](https://www.youtube.com/watch?v=EXIV6CxdseQ)
- [Video series - Estimation in Drupal Projects, Drupalize.me](https://drupalize.me/videos/estimation-drupal-projects?p=2203)

