# Drupal fixes and changes Report

> How to estimate the costs and time needed to fix issues or make changes to a Drupal website that you did not develop!
> Before giving a proposal (RFP) you need to inspect the site! But inspecting a Drupal site is not as simple as you believe...
> Here is a **basic checklist** of the Report that you need to deliver before doing anything on the site.

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
- [ ] Heatmap reports (eg using tools like [Hotjar](https://www.hotjar.com)).

### Drupal specific Reports
- [ ] Drupal content Structure (Content types, taxonomy etc)
- [ ] What is the main functionality (Features and Functionality, F&F) provided (eg login, register, add comments, share content etc)
- [ ] Drupal forms
- [ ] How many different pages are there
- [ ] Is there a mobile verison of the website or responsive css styles
- [ ] Usage of special modules (eg Panels, Features, Context, Paragraphs etc)
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

### Useful Drupal modules
- [advstatus (7.x)](https://www.drupal.org/project/advstatus)
- [forena (7.x, 8.x)](https://www.drupal.org/project/forena)
- [field_report (8.x)](https://www.drupal.org/project/field_report)
- [content_report (7.x)](https://www.drupal.org/project/content_report)
- [quant (7.x)](https://www.drupal.org/project/quant)
- [panels_pane_report (7.x)](https://www.drupal.org/project/panels_pane_report)
- [mysqlreport (7.x)](https://www.drupal.org/project/mysqlreport)
- [prod_check (7.x, 8.x)](https://www.drupal.org/project/prod_check)
- [d8_migration_check (7.x)](https://www.drupal.org/project/d8_migration_check)
- [site_audit (7.x, 8.x)](https://www.drupal.org/project/site_audit)
- [upgrade_check (6.x, 7.x)](https://www.drupal.org/project/upgrade_check)

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
- [The Gizra way pricing method](https://gist.github.com/theodorosploumis/826412bb5f2dd0aadf2728f950ffa225)
