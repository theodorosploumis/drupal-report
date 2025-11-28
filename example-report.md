# Drupal Best Practices - Project report

### 1. Parameters to consider

- Delivery under time pressure.
- Multilingual content.
- Accessibility Valid code (WCAG 2.0 level A).
- Anonymous users cannot create accounts.
- Content will be added manually.
- There is an existing old website (redesigned project).

---

### 2. Site building

#### 2.1 Nodes

- (✓) Entity and bundle name should use only singular name (Correct:  content type "page". Incorrect: content type "pages").
- (✓) Don't use nodes to create dynamic blocks (eg a block slideshow). Create a custom entity instead or better a custom block type.
- (✓) Create a new Node bundle only when this bundle needs to have different display options, different functionality, too many different fields and needs specific management.
- (✓) Less bundles is better for the database and performance but needs more manipulation.
- (✓) Don't create new revisions by default except if the Node pages you create need to have workflow statues and they are really important (eg a simple news page on a 10k News website may not have revisions but the main product landing page could have).
- (✓) Display view modes should be generic for all Content types and not specific (eg event_full).
- (x) Machine names of Content types and fields should disallow name conflicts (eg `field_category` vs `field_a_seasonal_category` and `body` vs `field_a_main_content`).
- (✓) Content types should follow this pattern for the machine name: [machinename]. That means you should use only letters and no special character or space.
- (✓) Avoid very generic machine names or names that have been used already on the site even for another type of functionality (Views, Content types, Blocks, Plugins etc).
- (x) For multiple reusable references use a custom entity and not Blocks (issue with the `field_a_walk_block` block reference field)
- (x) Node create forms seem too complicated to use.

#### 2.2 Blocks

- (x) Custom Blocks should follow this pattern for the machine name: [machinename]. That means you should use only letters and no special character or space. (`walk_blocks` instead of `walkblocks`)
- (x) Create custom Block Types using code. (created from the UI)
- (x) Treat machine_name, fields, view modes etc like any other Content type (see above). (`walk_blocks` instead of `walk`)
- (x) On the machine_name do not add the block prefix (Drupal will add this anyway before the machine_name). (`walk_blocks` instead of `walk`)
- (✓) On the machine_name do not add any region/theme/placement etc related info.

#### 2.3 Taxonomy

- (x) Entity and bundle name should use only singular name (Correct: vocabulary "author". Incorrect: vocabulary "authors"). (issues with all the machine names `article_categories, neighbourhoods_categories, seasonal_category` vs `article, neighbourhood, season`)
- (✓) Use taxonomy terms only when you need to show pages of categorized content.
- (✓) Don't use taxonomy terms just to filter content. Instead use list type fields.

#### 2.4 Fields

- (✓) Common fields should be named as generic as possible, but at the same time very clear (no common fields found)
- (x) Fields machine name should follow this pattern for the machine name:  `field_[content_type_machine_name]_[short_name]`. (issues with fields `field_a_, field_n_, field_m_a_` etc)
- (✓) Re-use fields (shared fields) only when you need to create a reference using this field or the field does not change at all between the shared entities (eg field created).
- (x) All fields require a Description to inform the user about their need. (issues with all fields)
- (x) Image fields file directory should not use the default structure `[date:custom:Y]-[date:custom:m]` but a custom one meaningful name (eg `banners`). Unify image fields of the same type under the same folders. (issues with all image fields)
- (x) Remove `gif` from allowed file extensions for image fields except if there are special requirements. (issues with all image fields)
- (x) Fields on Paragraps do not follow the field structure patterns.
- (x) Paragraphs have no image icons.
- (x) Paragraphs names and usage seem somehow unclear.

#### 2.5 (Drupal) Views

- (x) Views should follow this pattern for the machine name: [machinename]. That means you should use only letters and no special character or space. (issues with several Views)
- (x) Remove the suffix `_1` from the default machine name that Views create for a new Views display (eg "page_1" should be "page"). (issues with several Views)
- (x) It is required to give a meaningful (Administrative) name, description and tags to the Views. Do not leave the default values. (no )
- (x) Create one Views per Views Display except if it is a requirement. For example a Block Views and a Page Views for the same Content type should exist on different Views. (issues with Views `featured_articles` etc)
- (x) Always use `Format > Show: Content` for the views row display and not fields. This way the styling will be tied with the Content types View Modes. If there is no available content type View Mode create one. (many Views use fields instead of display modes)
- (✓) Do not add custom CSS classes on the whole Views.
- (✓) Always override default system views if they are to be used on the project.
- (✓) Do not use Ajax by default for a View.
- (x) Always provide a simple text for "No results behavior". (issues with several Views)
- (✓) Always use `Access: Permission | ...` for the Views access. Do not use Roles.
- (x) Add useful Administrative comments for each Views.
- (✓) Always provide a Title for the Views.
- (x) Disable all unused Views.

#### 2.6 Forms

- (✓) Use **core Contact form** only if there are no special requirements (eg one only contact form, no need to keep submissions, few filds only etc).

#### 2.7 Text formats and editors

- (x) Try to use only 1 HTML allowed editor format. Multiple HTML allowed formats will have issues with multiple authors with different editing permissions. (2 different HTML formats found)
- (x) Administrators should not use any extra format (full_html etc) that will not be available for Authors since all the Content must be editable by the portal Managers/Authors etc. (see above)
- (✓) Use CKEditor for HTML allowed format.
- (x) All users should not have the option to change between plain_text and html.
- (✓) Insecure piece of content (eg PHP) should be added programmatically from code and not on the wysiwyg textarea.
- (x) The WYSIWYG editor buttons should be the same as the HTML tags allowed. Nothing more, nothing less. (There are too many CKEditor tags that do not have a related button and also seem unused - eg `code`)
- (✓) WYSIWYG should inherit exactly the frontend Theme CSS/JS.
- (x) WYSIWYG should not allow the user to add styles that do not have a style.
- (✓) WYSIWYG should not allow the user to create functionality inside the Editor such as dropdown menus or effects.
- (x) For each allowed option on the Drupal text Filter WYSIWYG should provide the relative button. Eg if the user is able to add a `<blockquote>` she should see a button on the Editor to add a blockquote. (see above)
- (✓) WYSIWYG should provide basic information about using the Editor as also as a more analytic page for Admins.
- (x) Too many options on the WYSIWYG may cause problems. Protect the user from "breaking" the site design/code etc.
- (x) For accessibility valid code there should be forced elements on CKEditor (eg required alt attribute for images).

#### 2.8 Users, roles & permissions

- (?) Use an "Administrator" role only when you need to add more than 1 Administrators.
- (✓) Split roles by Persona (not by functionality).
- (?) Do not allow authors access pages and options that they have nothing to do (hide empty admin pages).
- (✓) Don't allow multiple real persons to share the same Drupal Account. Conmsider creating 1 account per person.
- (x) Give short one word machine names to user Roles (eg prefer "sitemanager" instead of "site_manager").
- () Do not add any permissions for the core user role "Authenticated User" (authenticated) except if there are no other member roles.
- (x) Short roles by permission quantity. For example Anonymous shoulld be on top and Administrators should be below any other roles.
- (?) Every custom module should define its own permissions. Never reuse an existing permission!
- (x) Use module [masquerade](https://www.drupal.org/project/masquerade) to test other members permissions.
- (x) Create **custom admin dashboards**, do not let authors use the default Drupal admin dashboard/backend.

---

### 3. Theming, templates

- (✓) Follow the [Atomic design](http://patternlab.io/about.html) philosophy for the CSS as also as for the design and html.
- (✓) Avoid using modules **panels, panelizer, panels_everywhere** and of this family.
- (-) Use preprocess functions on `.theme` file to add custom html classes or other attributes, twig variables etc.
- (x) Don't forget to create templates for special pages (404, 403, maintenance, login page etc).
- (x) For large projects with many templates investigate using modules [components](https://www.drupal.org/project/components), [ui_patterns](https://www.drupal.org/project/ui_patterns) and family, [pattern_library](https://www.drupal.org/project/pattern_library) as also as [Patternlab library](https://drupal-pattern-lab.github.io).
- (✓) Try to use only core theme ([Classy](http://cgit.drupalcode.org/drupal/tree/core/themes/classy)) as base theme.
- (✓) If you want to use a contrib base theme (eg bootstrap, omega etc) it is better to clone and override it and use no base theme.
- (✓) It is a good practice to have a project styleguide.
- (✓) For complicated content structure requirements investigate using module [paragraphs](https://www.drupal.org/project/paragraphs).
- (x) Consider using the most common breakpoints for responsive design and use the same breakpoints for Drupal breakpoints also (340px, 768px, 1024px, 1600px). (No `tia.breakpoints.yml` file found. Only on the CSS found the breakpoints.)
- (✓) Use SASS/SCSS.
- (✓) Support IE11 and above browsers and follow the [Drupal project browser support](https://www.drupal.org/docs/8/system-requirements/browser-requirements). We are not styling with that in mind but will deal with it when finished.
- (✓) Override only the necessary CSS coming from each module. Do not copy and paste all the CSS of a module to the project Theme.
- (✓) For the Admin pages use the default Core admin theme (Seven) and simply attach your CSS/JS files to add some functionality. This will happen on a custom module or a subtheme.
- (✓) If you want to override a twig template get only from the source module that provides that. Eg if you want to override the `html.html.twig` file copy that from the system module.
- (✓) Under the Theme folder create new subfolders to group files only if there is a significant amount of them and it makes sense to separate theme. Eg split the twig files to templates/system, templates/block etc using the pattern templates/[module] if there are 3 files of the system and 2 files of the block module.
- (✓) Avoid using the path alias (eg related classes) of a webpage to style the page. Path aliases are considered unstable and could change frequently.
- (x) Do not use non semantic CSS classes. Saying that we should not use classes such as "clearfix, container, full-width" etc if these classes are used to provide some CSS styling. Instead use SASS mixins such as `@full-width {width: 100%}`.
- (x) Avoid theming with elements except from the basic ones (p, h1 etc). Use CSS classes instead.
- (✓) If you need to use a CSS framework try to pick up only the required parts of the framework and not the whole framework.
- (✓) Always comment @mixins, @function.
- (✓) Always split large scss files if they contain too many lines. Split them by usage (eg the variables related to color, the variables related to typography etc).
- (✓) Useful plugins to use for theme development are [autoprefixer](https://autoprefixer.github.io), [breakpoint-sass](http://breakpoint-sass.com), [ModularScale](https://www.modularscale.com), [browsersync](https://browsersync.io), [sass sourcemaps](http://thesassway.com/intermediate/using-source-maps-with-sass).
- (x) Display modes for Paragraphs should not have detailed machine names (`content_right_circle_legend_left` instead of `content_mode_1`)
- (x) JS/CSS structure seem complicated and without usable documentation

---

### 4. Development

#### 4.1 Documentation

- (x) Create a README file written for humans where you store all the development steps. (_README on theme has no information_)

#### 4.2 Coding

- Use [drupal console](https://drupalconsole.com) to generate code (modules, plugins etc).

#### 4.3 VCS - git

- (✓) Use a git online UI (GitHub, Gitlab, Bitbucket etc). On the same system add your issues, documentation and [CI](http://cgit.drupalcode.org/drupal/tree/core/drupalci.yml) automation workflows.
- (✓) Prefer using the [Feature branch workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow) with 1 only master branch, feature specific branches (for tasks and development), pull requests fro feature branches and git tags for live environment and so on.

#### 4.4 Drupal scaffolding

- (✓) Use [Drupal scaffold](https://github.com/drupal-composer/drupal-scaffold) for Drupal initial build except if the hosting provider proposes a different method. Avoid using the [Drupal core composer.json](http://cgit.drupalcode.org/drupal/tree/composer.json) file.
- (✓) Use only 1 custom `settings.php` that includes environment specific additional settings files. Track the settings.php file on git but not the additional settings files.
- (x) Try to keep important Drupal settings on the settings.php additional files (eg enabled development modules, caching options, php ini settings etc) and not on the database.
- (✓) Settings.php and additional files should work on a CI system and they should be "platform agnostic".
- (✓) Use composer for dependencies and track only composer.json and composer.lock files on git.
- (✓) Try to not track composer downloaded files on git (eg module/contrib, themes/contrib, core, vendor folders etc). Track them only if you have no options to run `composer install` on the online servers.
- (x) Prefer using a specific version for all packages and especially for Drupal core (eg `"drupal/core": "8.6.10"` instead of `"drupal/core": "^8.6"`)
- (✓) Patches should be added with composer using [cweagans/composer-patches](https://github.com/cweagans/composer-patches).
- (✓) Keep the `config` folder out of the web files folder but track it on git.
- (✓) Keep the `vendor` folder out of the web files folder.
- (x) Scaffolding code should exist on the project root (eg ansible, bash, dockerfile etc) either to create the environment on a CI or a VM.
- (✓) Use `drush config-import/config-export` (or additional drush options like `drush csex/csim`) to manage config.
- (✓) Less modules is better.
- (✓) Try to use only core modules and add contributed modules only if required.

#### 4.5 Infrastructure

- (✓) Don't rise the recommended php memory_limit when there are relevant issues. Try to figure out what causes the memory_limit timeout.
- Run cron externally (disable core cron settings).
- Use a custom SMTP server to send emails.

#### 4.6 Backups

- Keep backups for the database with date specific pattern names (eg "livedb-2019-01-29T18:33:46+0200.sql.gz").
- User generated public or private files (eg sites/default/files) should be backup separately from the database.
- Always take a backup of current site before restoring a backup.

#### 4.7 Testing

- _No test found_.

#### 4.8 Third party libraries

- (✓) Prefer tiny and specific libraries.
- (✓) If you care about performance try to download the libraries locally instead of using a CDN source.

#### 4.9 Modules to use for development

- [stage_file_proxy](https://www.drupal.org/project/stage_file_proxy)
- [devel](https://www.drupal.org/project/devel)
- [masquerade](https://www.drupal.org/project/masquerade)
- [structure_sync](https://www.drupal.org/project/structure_sync)
- [config_split](https://www.drupal.org/project/config_split)
- [config_installer](https://www.drupal.org/project/config_installer)
- [backup_migrate](https://www.drupal.org/project/backup_migrate)

#### 4.10 Modules to avoid on live environments

- (core) dblog
- (core) automated_cron

---

### 5. Hosting

- When selecting hosting consider additional needs such as CDN, SSL, Monitoring, Development Automation, development tools available etc.
- In order to **support the project** technically (Drupal updates, security issues, technical support) use a hosting solution that allows to install drush, git, composer and supports system logging, cron jobs and ssh login. Otherwise use a Drupal specific hosting solution (**Acquia, Pantheon, Platform.sh**).
- If you want to host multiple similar sites with the same code base (multisites) investigate using [Aegir](http://www.aegirproject.org) solutions such as [BOA](https://github.com/omega8cc/boa).
- Don't use unmanaged servers except if you have a devops team with deep knowledge of Drupal hosting.

---

### 6. Project specific proposals

- Investigate using a content editind workflow system (core "workflows" module) because there are too many authors.
- Design and develop for WCAG accessibility from the beginning (don't leave that for the end of development).
- Core caching modules ("big_pipe, page_cache, dynamic_page_cache") will be enough for caching this project pages. You could only add [https://www.drupal.org/project/advagg](advagg) module if you need more control for caching.
- Some installed modules seem to be useless (eg core "color, quickedit, tour, history") probably because the profile "Standard" was selected initially.
- Creating new Content (eg Article) seem to be complicated with many options and no description/help for authors.
- Multilingual content may affect several content pages and functionality such as "Search page", "Related Content blocks" and other dynamic views.
- I like very much the idea of having only a few contrib modules.
- There are a few more modules that should be added later for sure (eg GDPR, xmlsitemap, pathauto, redirect, google_analytics, spam prevention, external links target, )
- Since there are only Authors from the same company/organization and anonymous users cannot create accounts I would recommend to use core "media libraries" for all the images used on the Node types and not only for some of the fields.
- CKEditor has no options (widget) to create links to internal pages.
- Since there is table button for CKEditor texareas this should be also designed to be responsive.
- I would propose to use a managed Drupal hosting service for sure.

---

### 7. Useful resources

- [DrupalTools](https://drupaltools.github.io)
- [Drupal Best Practices](https://github.com/theodorosploumis/drupal-best-practices)