# Certified Mautic Marketer — Certification Curriculum

**Target platform version:** Mautic 6.x
**Reference documentation baseline:** `https://docs.mautic.org/en/6.0/`
**Document status:** Draft v2.1 — curriculum outline for review

**Reference tiers used throughout:** **T1** `docs.mautic.org/en/6.0/` (primary) · **T2** `docs.mautic.org/en/7.0–7.1/` (cross-version fallback, used only where the 6.0 page is a stub or missing) · **T3** `kb.mautic.org` (official Knowledgebase) · **T4** `mautic.org` (feature pages, blog, case studies — non-procedural) · **T5** `community.mautic.org` (roadmap context). Every URL was individually loaded and verified. No third-party source is cited.

---

## 1. Core curriculum

### Domain A — Getting Started with Mautic (Modules 1–3)

---

#### Module 1 — Introduction to Mautic

**Learning objectives**
- Explain what Mautic is and the marketing problems it solves
- Describe how contacts, components, channels and campaigns relate to one another
- Identify where performance is assessed in the platform

**Key concepts to cover**
- What marketing automation is; what Mautic is and what it offers
- How Mautic works end to end
- Contact management as the core data layer
- Components vs Channels vs Campaigns
- Assessing performance

**Hands-on exercise**
Walk an existing contact record end to end and narrate which part of the platform generated each piece of activity.

**Official references**
- [Mautic overview](https://docs.mautic.org/en/6.0/overview/overview.html) — T1
- [What is Mautic?](https://kb.mautic.org/article/what-is-mautic.html) — T3
- [Getting started with Mautic](https://kb.mautic.org/article/getting-started-with-mautic.html) — T3, sections *What is Marketing automation?* / *What is Mautic?* / *What does Mautic offer?*

---

#### Module 2 — Mautic setup

**Learning objectives**
- Describe the available installation routes at an awareness level
- Identify what a marketer must confirm is in place before campaigns can run
- Deploy the tracking script and verify contacts are being tracked

**Key concepts to cover**
- Production package, GitHub, Composer and DDEV install routes (awareness only)
- Basic configuration after install
- Required cron jobs: segments, campaigns, custom fields
- Optional cron jobs: email queue, monitored inbox, imports/exports, scheduled broadcasts
- The tracking script: Global Configuration → Tracking Settings; the JS snippet; installing via a CMS integration
- Tracking depth: tracking pixel, embedding the pixel, identify visitors by tracking URL, how contacts are tracked, cookies used by Mautic (first-party and third-party)

**Hands-on exercise**
Audit a Mautic instance: confirm which required cron jobs are running, deploy the tracking script to a test site, and verify a visitor record is created.

**Official references**
- [Installation](https://docs.mautic.org/en/6.0/getting_started/how_to_install_mautic.html) — T1
- [Cron jobs](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html) — T1; [Segment cron jobs](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#segment-cron-jobs) · [Campaign cron jobs](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#campaign-cron-jobs) · [Custom Field cron jobs](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#custom-field-cron-jobs)
- [Tracking script](https://docs.mautic.org/en/6.0/configuration/tracking_script.html) — T1 *(short page, no subsections — supplement with the anchors below)*
- [Managing Contacts — Contact tracking](https://docs.mautic.org/en/6.0/contacts/manage_contacts.html#contact-tracking) — T1, the substantive coverage: [Tracking script JavaScript](https://docs.mautic.org/en/6.0/contacts/manage_contacts.html#tracking-script-javascript) · [Tracking pixel](https://docs.mautic.org/en/6.0/contacts/manage_contacts.html#tracking-pixel) · [How are Contacts tracked](https://docs.mautic.org/en/6.0/contacts/manage_contacts.html#how-are-contacts-tracked-with-the-tracking-script) · [Cookies used by Mautic](https://docs.mautic.org/en/6.0/contacts/manage_contacts.html#cookies-used-by-mautic)
- [Getting started with Mautic](https://kb.mautic.org/article/getting-started-with-mautic.html) — T3, sections *How to install Mautic?* / *How to set up basic configurations* / *What are cron jobs* / *How to add tracking pixel in Mautic*

---

#### Module 3 — UI walkthrough

**Learning objectives**
- Navigate the Mautic interface and locate each functional area
- Build and customise a Dashboard for a marketing team
- Use Categories and search operators to find and organise records

**Key concepts to cover**
- Guided tour of the main areas: Contacts, Channels, Segments, Campaigns, Components, Reports, Dashboard, Settings
- Dashboard: date range filter, widgets, widget ordering, dashboard import/export, widget cache, permissions
- Categories: creating and managing, using categories for contacts
- Search operators and per-entity search filters (Contacts, Segments, Emails, Forms, Landing Pages, Focus Items, Stages, Reports)
- The Publish/Unpublish control and where it applies across entities

**Hands-on exercise**
Build a marketing dashboard with at least four widgets, export it, and re-import it into a second user account. Then use search operators to isolate all contacts in a given segment who opened a specific email.

**Official references**
- [Getting started with Mautic](https://kb.mautic.org/article/getting-started-with-mautic.html) — **T3, primary source for this module.** Its walkthrough sections (*How to use Contacts* / *Channels* / *Segments* / *How to create your first Mautic Campaign* / *Exploring other features and how they work together*) name the actual main-menu areas in sequence — the closest thing Mautic publishes to an application tour.
- [Dashboard](https://docs.mautic.org/en/6.0/dashboard/dashboard.html) — T1
- [Categories](https://docs.mautic.org/en/6.0/categories/categories-overview.html) — T1
- [Working with Mautic Categories](https://kb.mautic.org/article/working-with-mautic-categories.html) — T3
- [Searching Mautic](https://docs.mautic.org/en/6.0/search/search_operators.html) — T1
- [Explaining the Publish/Unpublish feature](https://kb.mautic.org/article/explaining-the-publish-unpublish-feature.html) — T3, covers publish-up/publish-down scheduling across all eleven supported entity types

> **Gap resolution:** Mautic 6.0 has no dedicated UI/navigation page. The KB *Getting started* article is the official substitute and carries this module.

---

### Domain B — Configuration Essentials (Modules 4–6)

---

#### Module 4 — How to configure Mautic

**Learning objectives**
- Locate and interpret the configuration settings that affect marketing outcomes
- Configure email transport, tracking and frequency defaults
- Understand which settings are marketer-owned versus admin-owned

**Key concepts to cover**
- System settings and system defaults
- Email settings: transport, queue, mail send settings, default frequency rule, monitored inbox, unsubscribe settings, open and link tracking
- Contact settings: merge settings, list settings, import and export settings
- Segment, Company, Landing Page, Form, Tracking and Report settings
- Transactional vs marketing email and the consent implications

**Hands-on exercise**
Configure email open and link tracking, set a default frequency rule, and document the change in a configuration log.

**Official references**
- [Mautic configuration settings](https://docs.mautic.org/en/6.0/configuration/settings.html) — T1
- [Getting started with Mautic](https://kb.mautic.org/article/getting-started-with-mautic.html) — T3, section *How to set up basic configurations in Mautic?*
- [Understand the Difference: Transactional and Marketing Emails in Mautic](https://kb.mautic.org/article/understand-the-difference-transactional-and-marketing-emails-in-mautic.html) — T3

---

#### Module 5 — Users, roles and permissions

**Learning objectives**
- Create user accounts and assign appropriate roles
- Apply granular permissions so team members access only what they need

**Key concepts to cover**
- Creating a user: Settings → Users → +New; first/last name, roles, signature, position, credentials, time zone, language
- Password requirements; Mautic does **not** email login credentials — they must be provided directly
- Roles overview, full system access vs granular permissions
- Explaining the permission options

**Hands-on exercise**
Create a "Campaign Editor" role that can build and edit emails and campaigns but cannot publish or delete, then assign it to a test user and verify the restriction.

**Official references**
- [Managing Users](https://docs.mautic.org/en/6.0/users_roles/managing_users.html) — T1
- [Roles](https://docs.mautic.org/en/6.0/users_roles/managing_roles.html) — T1

---

#### Module 6 — How to integrate Mautic

**Learning objectives**
- Install and configure plugins from the Mautic Marketplace
- Map fields between Mautic and an external system
- Test and troubleshoot an integration

**Key concepts to cover**
- Using the Mautic Marketplace, plugin detail pages, versions and maintainers
- Installing plugins
- Field mapping between Mautic and third-party systems
- Testing integrations and troubleshooting plugins
- A worked CRM integration end to end

**Hands-on exercise**
Install one integration from the Marketplace, complete the field mapping for at least three contact fields, and run a test sync.

**Official references**
- [Mautic Marketplace](https://docs.mautic.org/en/6.0/marketplace/marketplace.html) — T1
- [Plugin resources](https://docs.mautic.org/en/6.0/plugins/plugin_resources.html) — T1
- [How to integrate Mautic with Salesforce](https://kb.mautic.org/article/how-to-integrate-mautic-with-salesforce.html) — T3, worked example
- [Salesforce plugin](https://docs.mautic.org/en/6.0/plugins/salesforce.html) · [HubSpot plugin](https://docs.mautic.org/en/6.0/plugins/hubspot.html) — T1

---

### Domain C — Mastering Contact Management (Modules 7–10)

---

#### Module 7 — Contact fundamentals

**Learning objectives**
- Distinguish between visitors (unidentified) and standard contacts
- Explain how Mautic tracks anonymous visitors and converts them to known contacts

**Key concepts to cover**
- Contact types: visitors (formerly "anonymous leads") vs standard contacts
- Changing the contact list view

**Hands-on exercise**
Identify a visitor record in the instance and trace which action converted a visitor into a known contact.

**Official references**
- [Contacts](https://docs.mautic.org/en/6.0/contacts/contacts_overview.html) — T1
- [Getting started with Mautic](https://kb.mautic.org/article/getting-started-with-mautic.html) — T3, section *How to use Contacts in Mautic?*

---

#### Module 8 — Adding contacts

**Learning objectives**
- Add contacts individually and in bulk
- Prepare and execute a compliant CSV import with correct field mapping
- Use a background import to avoid browser timeouts on large files

**Key concepts to cover**
- Quick add and Add new Contact
- Import file requirements and field mapping
- Types of import: browser-based vs background job
- Import job list, starting and stopping imports
- Exporting contact lists

**Hands-on exercise**
Import a 100-row CSV containing at least two custom fields using a background import job, then verify field mapping accuracy on five sample records.

**Official references**
- [Managing Contacts — Importing Contact lists](https://docs.mautic.org/en/6.0/contacts/manage_contacts.html#importing-contact-lists) — T1
- [Import Contacts](https://docs.mautic.org/en/6.0/contacts/import_contacts.html) — T1
- [How to import contacts to Mautic in the background without timing out](https://kb.mautic.org/article/how-to-import-contacts-to-mautic-in-the-background-without-timing-out.html) — T3

---

#### Module 9 — Managing contacts

**Learning objectives**
- Edit, merge, batch-action and organise contact records
- Read a contact's engagement history and interpret it for campaign decisions
- Create and publish custom fields and apply tags

**Key concepts to cover**
- Editing contacts, managing duplicates, merging two contacts, batch actions
- Individual contact details: engagements chart, history, notes, changing segments and campaigns
- Contact tracking: website monitoring, tracking pixel, mobile monitoring, cookies
- Custom fields: adding, publishing, locally defined countries and regions
- Tags: creating, adding to contacts, and using tags in campaigns, forms and segments

**Hands-on exercise**
Merge two duplicate contacts, add a custom field for "Industry", tag 20 contacts by industry via batch action, and use a tag-based segment filter to isolate them.

**Official references**
- [Managing Contacts](https://docs.mautic.org/en/6.0/contacts/manage_contacts.html) — T1
- [Manage Custom Fields](https://docs.mautic.org/en/6.0/contacts/custom_fields.html) — T1
- [Tags](https://docs.mautic.org/en/6.0/contacts/tags.html) — T1

---

#### Module 10 — Contact preferences and communication frequency

**Learning objectives**
- Configure frequency rules to control contact fatigue
- Build a preference centre and wire it into emails

**Key concepts to cover**
- Frequency rules: global and per-contact
- Preference centre: preferred channels and frequency, contact categories, contact segments, unsubscribe preferences
- Creating a Preference Center landing page, preference tokens, setting preference pages in emails
- Consent handling and its relationship to transactional vs marketing email

**Hands-on exercise**
Build a preference centre page with channel and category options and link it from an email footer using the correct preference token.

**Official references**
- [Frequency rules](https://docs.mautic.org/en/6.0/contacts/frequency_rules.html) — T1
- [Preference center](https://docs.mautic.org/en/6.0/contacts/preference_center.html) — T1
- [Understand the Difference: Transactional and Marketing Emails in Mautic](https://kb.mautic.org/article/understand-the-difference-transactional-and-marketing-emails-in-mautic.html) — T3, sections *Working with Consent in Mautic* / *Complying With Regulations*

---

### Domain D — Managing Companies and Organizations (Module 11)

---

#### Module 11 — Adding and managing companies

**Learning objectives**
- Create company records and associate contacts with them
- Apply company scoring and identify a contact's primary company
- Use company data in campaigns and segments

**Key concepts to cover**
- Creating and managing companies
- Company custom fields and company segments
- Identifying companies; company duplicates and merging companies
- Assigning companies to contacts: contact profile, contacts list view, via a campaign, through a form
- Company scoring and setting the primary company
- Company actions in campaigns; engagements/points chart

**Hands-on exercise**
Create five company records, auto-assign contacts through a form submission, set a primary company for a multi-company contact, and build a company-based segment.

**Official references**
- [Companies](https://docs.mautic.org/en/6.0/companies/companies_overview.html) — T1
- [Configuration settings — Company settings and Multiple Company management](https://docs.mautic.org/en/6.0/configuration/settings.html) — T1

---

### Domain E — Segmenting Your Leads (Modules 12–14)

---

#### Module 12 — Segment fundamentals

**Learning objectives**
- Create a segment and choose the correct type for a use case
- Explain how segments are kept current

**Key concepts to cover**
- Creating a segment; public segments and preference-centre availability; the published toggle
- Viewing contact segments; exporting contacts of a segment
- Deleting all contacts in a segment; deleting vs deactivating a segment
- Segment rebuild dependency on cron (`mautic:segments:update`)

**Hands-on exercise**
Create two segments for the same audience — one static, one dynamic — and compare membership after a data change and a cron run.

**Official references**
- [Managing Segments — Creating a Segment](https://docs.mautic.org/en/6.0/segments/manage_segments.html#creating-a-segment) — T1
- [How to create a segment](https://kb.mautic.org/article/how-to-create-a-segment.html) — T3
- [Cron jobs — Segment cron jobs](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#segment-cron-jobs) — T1
- [Getting started with Mautic](https://kb.mautic.org/article/getting-started-with-mautic.html) — T3, section *How to use Segments in Mautic*

---

#### Module 13 — Static segments

**Learning objectives**
- Populate a static segment through each supported method
- Choose static segmentation appropriately (event lists, imported lists, manual cohorts)

**Key concepts to cover**
- Static segments are not filter-based
- Manually moving contacts: batch updating contacts, adding individual contacts
- Using a campaign action to add to a segment
- Form submit action
- Points trigger
- CSV upload

**Hands-on exercise**
Populate one static segment using all five documented methods and verify the membership count after each.

**Official references**
- [Static Segments](https://docs.mautic.org/en/6.0/segments/manage_segments.html#static-segments) — T1
- [Manually moving Contacts](https://docs.mautic.org/en/6.0/segments/manage_segments.html#manually-moving-contacts) · [Using a Campaign action](https://docs.mautic.org/en/6.0/segments/manage_segments.html#using-a-campaign-action) · [Form submit action](https://docs.mautic.org/en/6.0/segments/manage_segments.html#form-submit-action) · [Points trigger](https://docs.mautic.org/en/6.0/segments/manage_segments.html#points-trigger) · [CSV upload](https://docs.mautic.org/en/6.0/segments/manage_segments.html#csv-upload) — T1
- [What is the difference between a static and dynamic segment in Mautic?](https://kb.mautic.org/article/what-is-the-difference-between-a-static-and-dynamic-segment-in-mautic.html) — T3, mirrors all five entry methods

---

#### Module 14 — Dynamic segments

**Learning objectives**
- Build filter-based segments using the correct operators
- Apply date filters, including relative and anniversary-style expressions
- Predict how contacts move into and out of a dynamic segment

**Key concepts to cover**
- How Mautic moves contacts in and out based on applied filters
- Configuring segment filters; AND/OR logic
- Operators; matching part of a string (starts with, ends with, contains, like `%`, regexp)
- Using date filters and date options — relative formats (`+1 day`, `-1 year`) and text formulas (`today`, `last week`, `birthday -7 days`)

**Hands-on exercise**
Build three dynamic segments: one behavioural (email opened), one demographic (custom field), one date-based (activity in the last 30 days). Verify each after a cron run.

**Official references**
- [Dynamic Segments](https://docs.mautic.org/en/6.0/segments/manage_segments.html#dynamic-segments) — T1
- [Configuring Segment filters](https://docs.mautic.org/en/6.0/segments/manage_segments.html#configuring-segment-filters) · [Operators](https://docs.mautic.org/en/6.0/segments/manage_segments.html#operators) · [Matching part of a string](https://docs.mautic.org/en/6.0/segments/manage_segments.html#matching-part-of-a-string) · [Using Date Filters](https://docs.mautic.org/en/6.0/segments/manage_segments.html#using-date-filters) · [Date options](https://docs.mautic.org/en/6.0/segments/manage_segments.html#date-options) — T1
- [How to create a date-based segment in Mautic](https://kb.mautic.org/article/how-to-create-a-date-based-segment-in-mautic.html) — T3
- [How to create a segment by matching part of a string](https://kb.mautic.org/article/how-to-create-a-segment-by-matching-part-of-a-string.html) — T3

---

### Domain F — Essential Mautic Components (Modules 15–20)

---

#### Module 15 — Working with assets

**Learning objectives**
- Upload, categorise and publish downloadable assets
- Track asset downloads as contact activity and attribute them with UTM codes
- Use a gated asset as a lead-capture mechanism

**Key concepts to cover**
- Managing assets and asset categories
- Creating a new asset: uploading, using remote assets, adding UTM codes
- Viewing, editing and deleting an asset
- Displaying assets directly in the browser

**Hands-on exercise**
Publish a gated PDF as an asset with UTM codes, deliver it via a form submit action, and confirm the download appears in the contact's history.

**Official references**
- [Assets](https://docs.mautic.org/en/6.0/components/assets.html) — T1
- [How To Capture Email Addresses Using A Form And Assets](https://kb.mautic.org/article/how-to-capture-email-addresses-using-a-form-and-assets.html) — T3, worked gated-asset pattern

---

#### Module 16 — Introduction to forms

**Learning objectives**
- Distinguish campaign forms from standalone forms and choose correctly
- Configure form-level settings and understand progressive profiling

**Key concepts to cover**
- Campaign Form — triggers a campaign on submission; fewer immediate submit actions
- Standalone Form — executes many submit actions immediately on submission
- Creating a new form; form details; configuring forms
- Progressive profiling
- Blocking form submissions from specified domains
- Reading form results

**Hands-on exercise**
Build one campaign form and one standalone form for the same offer and document which submit actions are available to each.

**Official references**
- [Forms — Creating a new Form](https://docs.mautic.org/en/6.0/components/forms.html#creating-a-new-form) — T1
- [Configuring Forms](https://docs.mautic.org/en/6.0/components/forms.html#configuring-forms) · [Progressive profiling](https://docs.mautic.org/en/6.0/components/forms.html#progressive-profiling) · [Blocking Form submissions from specified domains](https://docs.mautic.org/en/6.0/components/forms.html#blocking-form-submissions-from-specified-domains) — T1
- [Working with Forms in Mautic](https://kb.mautic.org/article/working-with-forms-in-mautic.html) — T3, sections *Types of forms* / *Setting up a form* / *Form Details* / *Form Fields* / *Form actions* / *Form results*

---

#### Module 17 — Creating various forms

**Learning objectives**
- Select and configure the correct field type for each data need
- Map form fields to contact and company fields
- Apply validation, CAPTCHA and conditional field logic
- Configure submit actions

**Key concepts to cover**
- Field types and field options: general, mapped field, validation, properties, attributes, behavior
- CAPTCHA
- Checkbox group, radio group and select fields; description area; file upload; text
- Field order
- Creating conditional form fields
- Form actions (submit actions)
- Layout control: applying CSS classes to lay a form out in two columns

**Hands-on exercise**
Build a multi-field registration form with a conditional field, CAPTCHA, a mapped custom field, and three submit actions (add to segment, send email, adjust points).

**Official references**
- [Fields](https://docs.mautic.org/en/6.0/components/forms.html#fields) · [Field options](https://docs.mautic.org/en/6.0/components/forms.html#field-options) · [Creating conditional Form fields](https://docs.mautic.org/en/6.0/components/forms.html#creating-conditional-form-fields) · [Form actions](https://docs.mautic.org/en/6.0/components/forms.html#form-actions) — T1
- [Working with Forms in Mautic](https://kb.mautic.org/article/working-with-forms-in-mautic.html) — T3
- [Guide: Make a Mautic form show in two columns](https://kb.mautic.org/article/guide-make-a-mautic-form-show-in-two-columns-works-for-landing-pages-and-embeds.html) — T3
- [How to validate Email addresses in a Mautic form using JavaScript](https://kb.mautic.org/article/how-to-validate-email-addresses-in-a-mautic-form-using-javascript.html) — T3

---

#### Module 18 — Embedding forms on webpages

**Learning objectives**
- Deploy a Mautic form on an external website using each supported method
- Choose the right embed method for a given CMS and tracking requirement

**Key concepts to cover**
- Adding forms to pages
- Via JavaScript (automatic embed)
- Via iframe
- Self-hosted (manual copy of the form markup)
- Shortcodes for WordPress and Joomla

**Hands-on exercise**
Embed the same form three ways — JavaScript, iframe and self-hosted — on test pages and compare tracking behaviour for each.

**Official references**
- [Adding Forms to Pages](https://docs.mautic.org/en/6.0/components/forms.html#adding-forms-to-pages) — T1
- [Via JavaScript](https://docs.mautic.org/en/6.0/components/forms.html#via-javascript) · [Via iframe](https://docs.mautic.org/en/6.0/components/forms.html#via-iframe) · [Self-hosted](https://docs.mautic.org/en/6.0/components/forms.html#self-hosted) · [Shortcodes](https://docs.mautic.org/en/6.0/components/forms.html#shortcodes) — T1
- [How To Have People Subscribe For Your Newsletter](https://kb.mautic.org/article/how-to-have-people-subscribe-for-your-newsletter.html) — T3
- [How To Set Up A Newsletter Campaign In Mautic — Step 2: Embed The Form On Your Website](https://kb.mautic.org/article/how-to-set-up-a-newsletter-campaign-in-mautic.html) — T3

---

#### Module 19 — Introduction to landing pages and building landing pages

**Learning objectives**
- Create a landing page in Mautic and apply a theme
- Use the drag-and-drop builder to construct a responsive page
- Work with landing page drafts, preview and publish scheduling
- Build a Preference Center landing page

**Key concepts to cover**
- Setting up a simple landing page end to end
- The GrapesJS builder: drag & drop blocks, styling, responsive design, structure panel, code view, asset manager
- Enabling the builder; switching back to the legacy builder
- Templates and themes; custom fonts
- Landing page drafts: Save as Draft / Apply Draft / Discard Draft; one draft per page; previewing a draft by appending `/draft` to the preview URL
- Publish-up and publish-down scheduling against the system timezone
- Embedding a form and a Code/Raw HTML block on a page
- Customizing the Preference Center

**Hands-on exercise**
Build a landing page with a hero, an embedded form and an asset download link, applied to a chosen theme. Save a draft, preview it, then schedule it to publish for a fixed window.

**Official references**
- [Getting started with Mautic — *2. Set up a simple landing page*](https://kb.mautic.org/article/getting-started-with-mautic.html) — **T3, the only official step-by-step landing page walkthrough Mautic publishes**
- [Email & Landing Page Builder](https://docs.mautic.org/en/6.0/builders/email_landing_page.html) — T1, the builder itself
- [Landing Pages — drafts and preview](https://docs.mautic.org/en/7.1/components/landing_pages.html) — **T2 (7.1)**; sections *Landing Page drafts* / *Creating a draft Landing Page* / *Previewing a Draft Landing Page*. Used because the 6.0 page at the same path is an empty stub.
- [Explaining the Publish/Unpublish feature](https://kb.mautic.org/article/explaining-the-publish-unpublish-feature.html) — T3, includes a worked landing-page scheduling use case
- [Manage Themes](https://docs.mautic.org/en/6.0/themes/manage_themes.html) — T1
- [Guide: Make a Mautic form show in two columns — Option A: Mautic Landing Page](https://kb.mautic.org/article/guide-make-a-mautic-form-show-in-two-columns-works-for-landing-pages-and-embeds.html) — T3
- [Landing Pages](https://docs.mautic.org/en/6.0/components/landing_pages.html) — T1 *(stub — cite for the Preference Center heading only)*

> **Gap resolution:** the 6.0 landing-pages page is an empty stub (also stubbed in 5.2 and 4.x). This module is carried by the KB *Getting started* walkthrough, the Builder page, the 7.1 drafts/preview content, and the KB Publish/Unpublish article. Landing page **A/B testing** still has no official how-to — see [Section 3](#3-remaining-documentation-gaps).

---

#### Module 20 — Dynamic web content

**Learning objectives**
- Explain how Dynamic Web Content personalises a webpage per visitor
- Implement DWC slots on a website
- Build both campaign-based and filter-based dynamic content

**Key concepts to cover**
- Preparation; website configuration; Mautic configuration
- Creating Dynamic Web Content slots
- Campaign-based DWC: creating the request, creating the filters, pushing the content
- Filter-based DWC: creating filters
- Implementing DWC and setting default content
- Slot markup: `<div data-slot="dwc" data-param-slot-name="myslot">`, plus WordPress `[mautic type="content" slot="..."]` and Joomla `{mautic type="content" slot="..."}` shortcodes

**Hands-on exercise**
Place a DWC slot on a test page with default content, then serve two different variants — one campaign-driven, one filter-driven — and verify each renders for the right contact.

**Official references**
- [Dynamic Web Content](https://docs.mautic.org/en/6.0/components/dynamic_web_content.html) — T1
- [Creating Dynamic Web Content slots](https://docs.mautic.org/en/6.0/components/dynamic_web_content.html#creating-dynamic-web-content-slots) · [Campaign-based DWC](https://docs.mautic.org/en/6.0/components/dynamic_web_content.html#campaign-based-dynamic-web-content) · [Filter-based DWC](https://docs.mautic.org/en/6.0/components/dynamic_web_content.html#filter-based-dynamic-web-content) · [Implementing DWC](https://docs.mautic.org/en/6.0/components/dynamic_web_content.html#implementing-dynamic-web-content) — T1

---

### Domain G — Exploring Mautic Channels (Modules 21–25)

---

#### Module 21 — Introduction to emails

**Learning objectives**
- Choose between Template and Segment (Broadcast) emails
- Personalise emails with tokens, signatures and owner-based sending
- Send, schedule and test an email
- Configure tracking, unsubscribes and bounce handling

**Key concepts to cover**
- Email types: Template emails, Segment (Broadcast) emails, excluding segments
- Email formats
- Managing emails: email overview, drafts, previewing drafts, translations, cloning
- Tokens: default value, encoded value, date formats
- Mailer as owner; sending from the contact owner; overriding the setting
- Signatures
- **Scheduling a send** via the Publish/Unpublish option plus the `mautic:broadcasts:send` cron job; the email must have a published date and be currently published
- Testing an email before sending
- Tracking opened emails and tracking links in emails
- Unsubscribing; online version; contact replies
- Bounce management: monitored inbox, webhook bounce management, segment of bounced emails
- Troubleshooting emails

**Hands-on exercise**
Create one template email and one segment email for the same message. Schedule the segment email to send at a set time, verify the broadcast cron fires it, then build a segment of bounced addresses.

**Official references**
- [Emails](https://docs.mautic.org/en/6.0/channels/emails.html) — T1
- [Email types](https://docs.mautic.org/en/6.0/channels/emails.html#email-types) · [Template Emails](https://docs.mautic.org/en/6.0/channels/emails.html#template-emails) · [Segment (Broadcast) Emails](https://docs.mautic.org/en/6.0/channels/emails.html#segment-broadcast-emails) · [Tokens](https://docs.mautic.org/en/6.0/channels/emails.html#tokens) · [Tracking Opened Emails](https://docs.mautic.org/en/6.0/channels/emails.html#tracking-opened-emails) · [Bounce management](https://docs.mautic.org/en/6.0/channels/emails.html#bounce-management) · [Troubleshooting Emails](https://docs.mautic.org/en/6.0/channels/emails.html#troubleshooting-emails) — T1
- [How to send an Email at a scheduled time](https://kb.mautic.org/article/how-to-send-an-email-at-a-scheduled-time.html) — **T3, closes the scheduling gap**; sections *Setting up the scheduled Emails* / *The Cron job needed for scheduling emails*
- [Cron jobs — Send scheduled broadcasts (Segment Emails)](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#send-scheduled-broadcasts-segment-emails-cron-job) — T1; `mautic:broadcasts:send`
- [Cron jobs — Process Email queue](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#process-email-queue-cron-job) — T1
- [How to test emails in Mautic](https://kb.mautic.org/article/how-to-test-emails-in-mautic.html) — T3
- [Email sending doesn't work — here are 10 things to check](https://kb.mautic.org/article/email-sending-doesn-039%3Bt-work-here-are-10-things-to-check.html) — T3

---

#### Module 22 — Designing email templates

**Learning objectives**
- Build a branded, responsive email template using the builder
- Install, preview and manage themes
- Run an A/B test on a segment email and declare a winner
- Understand how MJML/HTML themes are structured and packaged

**Key concepts to cover**
- Email builder overview; enabling the builder
- Templates, themes, custom fonts
- Switching back to the legacy builder
- Installing, previewing, hiding, downloading and deleting a theme; assigning a default theme
- Why use email themes; HTML vs MJML markup; head and body components; image asset relative URLs; saving the theme package
- **A/B testing:** create the parent → create the variant → set traffic weight (the sum across all variants must be ≤ 100%) → choose winner criteria (asset download rate, email read rate, clickthrough rate, form submission rate) → declare a winner. **A/B testing is available for Segment emails only.**
- Translations, and previewing A/B and translation variants

**Hands-on exercise**
Install a theme, build a branded template email from it with a header, two content blocks and a footer containing the unsubscribe and preference-centre links. Then create a segment email with two subject-line variants at 50/50 weight and set clickthrough rate as the winner criterion.

**Official references**
- [Email & Landing Page Builder](https://docs.mautic.org/en/6.0/builders/email_landing_page.html) — T1
- [Manage Themes](https://docs.mautic.org/en/6.0/themes/manage_themes.html) — T1
- [Creating Themes](https://docs.mautic.org/en/6.0/builders/creating_themes.html) — T1
- [How to create an A/B test for emails in Mautic](https://kb.mautic.org/article/how-to-create-an-a-b-test-for-emails-in-mautic.html) — **T3, closes the email A/B testing gap**; sections *Create the parent* / *Create the variant* / *Create additional variants* / *Working with variants* / *Emails With Variants*
- [Emails — Translations](https://docs.mautic.org/en/6.0/channels/emails.html#translations) — T1, variant preview note

---

#### Module 23 — Introduction to Focus Items

**Learning objectives**
- Explain what a Focus Item is and when to use one
- Configure engagement triggers and frequency
- Deploy a Focus Item and measure its performance

**Key concepts to cover**
- Focus Item settings
- Engagement options: animate; when to engage (upon arrival, after slight scroll, scroll to middle, scroll to bottom, visitor intends to leave); timeout before engage; how often to engage (every page / once per session / every 2 or 15 minutes / hourly / daily); stop engaging after conversion; stop engaging after closing
- Content: basic, editor, HTML
- Colors
- Creating a Focus Item and using the Focus Item builder
- Deploying to a website; deploying through a campaign
- Measuring success
- UTM tagging a Focus Item for attribution

**Hands-on exercise**
Create an exit-intent Focus Item, deploy it to a test page, and configure it to stop engaging after conversion. Review its performance metrics after test traffic.

**Official references**
- [Focus Items](https://docs.mautic.org/en/6.0/channels/focus_items.html) — T1
- [Engagement options](https://docs.mautic.org/en/6.0/channels/focus_items.html#engagement-options) · [Creating a Focus Item](https://docs.mautic.org/en/6.0/channels/focus_items.html#creating-a-focus-item) · [Using the Focus Item builder](https://docs.mautic.org/en/6.0/channels/focus_items.html#using-the-focus-item-builder) · [Deploying to a website](https://docs.mautic.org/en/6.0/channels/focus_items.html#deploying-to-a-website) · [Deploying through a Campaign](https://docs.mautic.org/en/6.0/channels/focus_items.html#deploying-through-a-campaign) · [Measuring success](https://docs.mautic.org/en/6.0/channels/focus_items.html#measuring-success) — T1
- [UTM tags — Using UTM tags in Focus Items](https://docs.mautic.org/en/6.0/channels/utm_tags.html#using-utm-tags-in-focus-items) — T1
- [How To Capture Email Addresses Using An Exit Intent Popup](https://kb.mautic.org/article/how-to-capture-email-addresses-using-an-exit-intent-popup.html) — T3, adjacent use case

---

#### Module 24 — Exploring the different Focus Items

**Learning objectives**
- Correctly distinguish Focus Item **types** from Focus Item **styles**
- Select the right type and style combination for a marketing objective

**Key concepts to cover**

*Types of Focus Item — the three officially documented types:*

| Type | Purpose |
|---|---|
| Collect Data | Presents a form (which must already exist) within the Focus Item |
| Display a Notice | Presents a message to visitors |
| Emphasize a link | Drives visitors to a specific link |

*Styles — the four display formats:* Bar, Modal, Notification, Full page

**Hands-on exercise**
Build three Focus Items — one of each type — and present the same one in two different styles. Justify each type/style pairing against a stated marketing goal.

**Official references**
- [Types of Focus Item](https://docs.mautic.org/en/6.0/channels/focus_items.html#types-of-focus-item) — T1
- [Styles](https://docs.mautic.org/en/6.0/channels/focus_items.html#styles) — T1: [Bar](https://docs.mautic.org/en/6.0/channels/focus_items.html#bar) · [Modal](https://docs.mautic.org/en/6.0/channels/focus_items.html#modal) · [Notification](https://docs.mautic.org/en/6.0/channels/focus_items.html#notification) · [Full page](https://docs.mautic.org/en/6.0/channels/focus_items.html#full-page)

> **Exam-writing note:** "Types" and "Styles" are commonly conflated. This distinction is a strong candidate for a discriminating exam question. Note also that the Knowledgebase has **no** Focus Item article — the 6.0 docs are the sole source, and they are complete.

---

#### Module 25 — Creating marketing messages

**Learning objectives**
- Explain how a Marketing Message delivers on a contact's preferred channel
- Create a Marketing Message across multiple channels
- Predict channel fallback behaviour under frequency rules

**Key concepts to cover**
- What Marketing Messages are: one message, delivered on the channel the contact prefers
- Email as the default channel when no preference is set
- Channels must be configured first or they do not appear as options
- Enabling each channel and selecting or creating the message
- Interaction with frequency rules and per-channel pausing — when a limit is exceeded Mautic uses another channel with available frequency
- Sending text messages as a Marketing Message

**Hands-on exercise**
Create a Marketing Message with email and SMS variants, set a contact's channel preference in the preference centre, and confirm delivery follows the preference.

**Official references**
- [Marketing Messages](https://docs.mautic.org/en/6.0/channels/marketing_messages.html) — T1
- [What are Marketing Messages?](https://docs.mautic.org/en/6.0/channels/marketing_messages.html#what-are-marketing-messages) · [Creating a Marketing Message](https://docs.mautic.org/en/6.0/channels/marketing_messages.html#creating-a-marketing-message) — T1
- [SMS — Sending Text Messages as a Marketing Message](https://docs.mautic.org/en/6.0/channels/sms.html#sending-text-messages-as-a-marketing-messages) — T1
- [Preference center](https://docs.mautic.org/en/6.0/contacts/preference_center.html) — T1

> **Curriculum note:** "Dynamic Web Content" appears twice in the source outline — under Components and again under Channels. It is taught once, in **Module 20**. Reference it here as the on-site personalisation channel that complements Focus Items.

---

### Domain H — Crafting Campaigns (Modules 26–29)

---

#### Module 26 — Introduction to campaigns

**Learning objectives**
- Distinguish the three campaign models and select the right one
- Explain why a campaign is used rather than a one-off send
- Explain how contacts enter and progress through a campaign

**Key concepts to cover**
- Why use a campaign
- Campaign types
- Time-driven campaigns
- Contact-driven campaigns
- Mixed campaigns

**Hands-on exercise**
Given three marketing briefs, classify each as time-driven, contact-driven or mixed, and justify the choice.

**Official references**
- [Campaigns overview](https://docs.mautic.org/en/6.0/campaigns/campaigns_overview.html) — T1
- [Campaign types](https://docs.mautic.org/en/6.0/campaigns/campaigns_overview.html#campaign-types) · [Time driven Campaigns](https://docs.mautic.org/en/6.0/campaigns/campaigns_overview.html#time-driven-campaigns) · [Contact driven Campaigns](https://docs.mautic.org/en/6.0/campaigns/campaigns_overview.html#contact-driven-campaigns) · [Mixed Campaigns](https://docs.mautic.org/en/6.0/campaigns/campaigns_overview.html#mixed-campaigns) — T1
- [Creating Campaigns](https://kb.mautic.org/article/creating-campaigns.html) — T3, sections *Why use a campaign* / *How to create your first campaign* / *Campaign builder* / *Event Types*

---

#### Module 27 — Creating campaign forms and emails

**Learning objectives**
- Identify and prepare the prerequisites a campaign depends on
- Build the specific forms and emails a campaign will call

**Key concepts to cover**
- Campaign prerequisites — segments, forms and emails must exist first
- Campaign forms vs standalone forms in a campaign context
- Template emails as campaign-callable assets
- Creating text messages from the campaign builder

**Hands-on exercise**
Prepare a complete campaign asset set before building any campaign: one segment, one campaign form, three template emails and one landing page.

**Official references**
- [Creating Campaigns — Prerequisites](https://docs.mautic.org/en/6.0/campaigns/creating_campaigns.html#prerequisites) — T1
- [Forms — Creating a new Form](https://docs.mautic.org/en/6.0/components/forms.html#creating-a-new-form) — T1
- [Emails — Template Emails](https://docs.mautic.org/en/6.0/channels/emails.html#template-emails) — T1
- [Creating Text Messages from Campaign Builder](https://docs.mautic.org/en/6.0/channels/sms.html#creating-text-messages-from-campaign-builder) — T1
- [How To Set Up A Newsletter Campaign In Mautic — Steps 1, 3, 4](https://kb.mautic.org/article/how-to-set-up-a-newsletter-campaign-in-mautic.html) — T3, worked asset-preparation sequence

---

#### Module 28 — Building new campaigns

**Learning objectives**
- Build a campaign in the Campaign Builder using contact sources, decisions, actions and conditions
- Read and construct green and red paths correctly
- Apply delays, smart scheduling and date-based triggers

**Key concepts to cover**
- Creating a campaign; contact sources — contact segments and contact forms, and mixing both
- **Decisions** — what the contact does
- **Actions** — what Mautic does
- **Conditions** — what is true about the contact
- Green paths (positive/affirmative) and red paths (non-action)
- Notes on campaign actions; notes on delayed conditions and dates
- Using a custom date field to trigger a campaign
- Smart event schedule; scheduling events; triggering campaign events; cloning campaign events
- Adding or removing contacts in batch

**Hands-on exercise**
Build a five-step campaign containing at least one decision with both green and red paths, one condition, one delay and one action that changes segment membership. Launch it against a test segment.

**Official references**
- [Creating Campaigns](https://docs.mautic.org/en/6.0/campaigns/creating_campaigns.html) — T1
- [Using the Campaign Builder](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html) — T1
- [Getting started with Campaign Builder](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html#getting-started-with-campaign-builder) · [Decisions](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html#decisions) · [Actions](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html#actions) · [Conditions](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html#conditions) · [Green paths](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html#green-paths) · [Red paths](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html#red-paths) · [Smart event schedule](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html#smart-event-schedule) — T1
- [Creating Campaigns](https://kb.mautic.org/article/creating-campaigns.html) — T3, sections *Adding events* / *Event Types* / *Actions* / *Conditions* / *Scheduling events*
- [Getting started with Mautic — *How to create your first Mautic Campaign?*](https://kb.mautic.org/article/getting-started-with-mautic.html) — T3

---

#### Module 29 — Managing and troubleshooting campaigns

**Learning objectives**
- Monitor a running campaign and interpret its statistics
- Build a report to measure campaign performance
- Diagnose the common reasons a campaign step fails to fire
- Stop a running campaign safely

**Key concepts to cover**
- The campaign overview screen: Details drop-down, Campaign Statistics panel, Preview / Decisions / Actions / Conditions / Contacts tabs, Recent Activity panel
- Building a report against the **Campaigns — Campaign Events** data source for real metrics
- Why page visits are not recognised: testing while logged in as an admin, contact not in the campaign, sequential execution, URL wildcard matching
- Campaign cron dependency (`mautic:campaigns:update`, `mautic:campaigns:trigger`)
- Stopping a campaign by unpublishing it

**Hands-on exercise**
Deliberately break a campaign (e.g. a page-visit decision that never fires), diagnose it against the troubleshooting page, and fix it. Then build a report on campaign events to quantify drop-off.

**Official references**
- [Managing Campaigns](https://docs.mautic.org/en/6.0/campaigns/managing_campaigns.html) — T1 *(screen tour only — see note)*
- [Troubleshooting Campaigns](https://docs.mautic.org/en/6.0/campaigns/troubleshooting_campaigns.html) — T1
- [Reports — Data sources](https://docs.mautic.org/en/6.0/reports/reports.html#data-sources) — T1, **the only official route to real campaign metrics**
- [Cron jobs — Campaign cron jobs](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#campaign-cron-jobs) — T1
- [How do I stop a campaign running?](https://kb.mautic.org/article/how-do-i-stop-a-campaign-running.html) — T3

> **Documentation note:** `managing_campaigns.html` names each panel on the campaign overview screen but does not explain how to interpret them — it answers "what is on this screen", not "is my campaign working". There is no official page anywhere on reading campaign statistics. Reports is the substitute. Author interpretive guidance for this module.

---

### Domain I — Leveraging Points and Stages (Modules 30–33)

---

#### Module 30 — Manage actions (point actions)

**Learning objectives**
- Define point actions that award or deduct points from contact behaviour
- Design a scoring model that reflects real buying intent
- Apply decay and suppression to keep scores meaningful

**Key concepts to cover**
- Point actions: "those times when a Contact receives a change in their Point total" — positive or negative, based on a determined action
- Behaviours that can award points
- Mapping trust and intent: low value, high value, decreasing value actions
- Decay models and suppression segments
- Points troubleshooting: point actions fire only once per contact; do not register for logged-in admins; URL patterns must match exactly or use wildcards

**Hands-on exercise**
Build a five-action scoring model (page visit, form submit, email open, email click, asset download) and validate that scores accrue correctly on a test contact.

**Official references**
- [Points — Point Actions](https://docs.mautic.org/en/6.0/points/points.html#point-actions) — T1
- [Points troubleshooting](https://docs.mautic.org/en/6.0/points/points_troubleshooting.html) — T1
- [Lead scoring best practices with Mautic](https://kb.mautic.org/article/lead-scoring-best-practices-with-mautic.html) — T3, sections *Mapping trust and intent* / *Low value* / *High value* / *Decreasing value* / *Using a suppression segment* / *Decay model*

---

#### Module 31 — Manage triggers (point triggers)

**Learning objectives**
- Configure point triggers that fire once a point threshold is reached
- Distinguish triggers from actions confidently
- Build an MQL alert from a point threshold

**Key concepts to cover**
- Point triggers: once a contact has accumulated a point total, trigger an action — fired on reaching a minimum point threshold
- Campaign triggers, contact triggers, email triggers, add-on triggers
- Designing an MQL alert: when to trigger it, and who should receive it

**Hands-on exercise**
Create a trigger that, at 50 points, adds the contact to an "MQL" segment and notifies the contact owner.

**Official references**
- [Points — Point Triggers](https://docs.mautic.org/en/6.0/points/points.html#point-triggers) — T1
- [Campaign triggers](https://docs.mautic.org/en/6.0/points/points.html#campaign-triggers) · [Contact triggers](https://docs.mautic.org/en/6.0/points/points.html#contact-triggers) · [Email triggers](https://docs.mautic.org/en/6.0/points/points.html#email-triggers) — T1
- [Lead scoring best practices with Mautic](https://kb.mautic.org/article/lead-scoring-best-practices-with-mautic.html) — T3, sections *Creating an MQL alert campaign* / *When do we trigger the MQL alert?* / *Who should receive the MQL?*

> **Exam-writing note:** Actions *award or deduct* points from behaviour; Triggers *fire events* once a total is reached. This is a high-value discriminating question.

---

#### Module 32 — Point groups

**Learning objectives**
- Score contacts on multiple independent scales rather than one global total
- Use point groups across campaigns, forms, segments and reports

**Key concepts to cover**
- Managing point groups; point groups usage
- Using point actions and point triggers with groups
- Campaign condition; campaign action; form action; segment filters
- Contact details; group report; webhooks

**Hands-on exercise**
Create two point groups (e.g. "Product Interest" and "Engagement"), score against both, and build a segment that requires a threshold in each.

**Official references**
- [Point Groups](https://docs.mautic.org/en/6.0/points/point_groups.html) — T1

---

#### Module 33 — Stages

**Learning objectives**
- Model a marketing lifecycle using stages
- Move contacts between stages and visualise progression
- Align stages to a business workflow

**Key concepts to cover**
- What stages are and why they are used
- Creating stages: name, description, **weight**, published/active state
- The weight rule — contacts only move to a stage of equal or higher weight
- Moving contacts between stages **requires a campaign action** ("Change Contact's Stage"); stage changes are campaign-driven, not manual
- Visualising stage movement
- Lifecycle; aligning stages with business workflows

**Hands-on exercise**
Define a four-stage lifecycle (Subscriber → Lead → MQL → SQL), build the campaign actions that move contacts between them, and review the stage movement visualisation.

**Official references**
- [Stages](https://docs.mautic.org/en/6.0/stages/stages.html) — T1
- [Creating Stages](https://docs.mautic.org/en/6.0/stages/stages.html#creating-stages) · [Moving Contacts between Stages](https://docs.mautic.org/en/6.0/stages/stages.html#moving-contacts-between-stages) · [Visualizing Stage movement](https://docs.mautic.org/en/6.0/stages/stages.html#visualizing-stage-movement) · [Lifecycle](https://docs.mautic.org/en/6.0/stages/stages.html#lifecycle) — T1
- [Working with Stages in Mautic](https://kb.mautic.org/article/working-with-stages-in-mautic.html) — T3, sections *What are stages?* / *Why use stages in marketing?* / *How to set up stages* / *How to transition users through the stages using campaigns* / *How to align stages with your business workflows*

---

### Domain J — Real-World Campaign Examples (Modules 34–37)

> **Scope note.** Mautic 6.0 ships **no example campaigns and no template library**. Official worked examples exist for the welcome/drip case (Knowledgebase) and, in narrative form, for an event campaign (case study) and a feedback-loop campaign (Knowledgebase). Where no worked example exists, the module is taught as an **applied build exercise** composing techniques from Modules 1–33, with official references given for every underlying mechanic.

---

#### Module 34 — Welcome series campaign

**Learning objectives**
- Build a multi-email onboarding sequence with time delays and behavioural branching
- Implement double opt-in as the entry point

**Key concepts to cover**
- **Time-based drip pattern:** segment entry → email 1 immediately → +7 days email 2 → +14 days email 3
- **Condition-based branching:** "Email sent" trigger → "Opened email" decision → green path email 1.2; red path waits 1 day then sends email 1.3; 7-day gap before the next branch
- **Double opt-in structure:** subscription form → add to "Newsletter Pending Opt-In" → send opt-in email → "visits verification page" decision → yes: swap to "Newsletter Subscription" segment + send welcome email; no: wait 2 days and resend
- Three-segment model: pending / confirmed / welcomed
- Monitoring subscriptions and best practices

**Hands-on exercise**
Build a complete double opt-in welcome series: form → confirmation email → welcome email → two-email nurture with an open-based branch. Test the form end to end.

**Official references**
- [How to create a drip campaign in Mautic](https://kb.mautic.org/article/how-to-create-a-drip-campaign-in-mautic.html) — **T3, the strongest worked example in the ecosystem**; sections *What is a drip campaign* / *Planning a Drip Campaign* / *Time-based Campaign* / *User condition based Campaign*
- [How To Set Up A Newsletter Campaign In Mautic](https://kb.mautic.org/article/how-to-set-up-a-newsletter-campaign-in-mautic.html) — T3, full seven-step double opt-in build
- [Creating a Double Opt-In Email Campaign](https://mautic.org/blog/creating-a-double-opt-in-email-campaign/) — T4, step-by-step breakdown
- [How To Have People Subscribe For Your Newsletter](https://kb.mautic.org/article/how-to-have-people-subscribe-for-your-newsletter.html) — T3
- [Using the Campaign Builder](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html) · [Form actions](https://docs.mautic.org/en/6.0/components/forms.html#form-actions) · [Template Emails](https://docs.mautic.org/en/6.0/channels/emails.html#template-emails) — T1

---

#### Module 35 — Event promotion campaign

**Learning objectives**
- Build a time-driven campaign anchored to a fixed event date
- Combine registration capture, progressive profiling, reminder sequencing and post-event follow-up

**Key concepts to cover**
- Time-driven campaign model
- Officially documented event campaign shape: invitation email with registration link → immediate confirmation → **progressive profiling** captures additional attributes incrementally across touches → pre-event logistics email → one automated reminder to non-registrants → post-event follow-up
- Registration form as the campaign entry point
- Segment separation of registrants vs non-registrants
- Delay-based reminder sequencing
- Focus Item or landing page for on-site promotion
- UTM tagging for attribution
- **Known platform limitation:** Mautic cannot natively segment by time-of-day, which constrains "X hours before the event" reminders. Teach date-level reminders and note the constraint.

**Hands-on exercise**
Build an end-to-end webinar promotion campaign: landing page + registration form with progressive profiling, three-email reminder sequence, a Focus Item promoting the event, and a post-event follow-up split by attendance.

**Official references**

*No step-by-step official tutorial exists for this campaign type. The one official end-to-end account is a case study; the mechanics are fully documented.*

- [Streamlining event communication with progressive profiling for a trust company](https://mautic.org/case-study/streamlining-event-communication-with-progressive-profiling-for-a-trust-company/) — **T4, the only official Mautic page describing an end-to-end event campaign.** Narrative case study, not a builder tutorial.
- [Campaigns overview — Time driven Campaigns](https://docs.mautic.org/en/6.0/campaigns/campaigns_overview.html#time-driven-campaigns) — T1
- [Using the Campaign Builder](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html) — T1
- [Forms — Progressive profiling](https://docs.mautic.org/en/6.0/components/forms.html#progressive-profiling) — T1
- [Email & Landing Page Builder](https://docs.mautic.org/en/6.0/builders/email_landing_page.html) — T1
- [Focus Items](https://docs.mautic.org/en/6.0/channels/focus_items.html) — T1
- [UTM tags](https://docs.mautic.org/en/6.0/channels/utm_tags.html) — T1
- [How to Grow your Community with Mautic](https://kb.mautic.org/article/how-to-grow-your-community-with-mautic.html) — T3, webinar-as-lead-magnet framing

---

#### Module 36 — Birthday greetings campaign

**Learning objectives**
- Build a recurring date-triggered campaign
- Apply anniversary and date-formula segment filters correctly
- Anticipate the documented limitations of date-based triggering

**Key concepts to cover**
- Using a custom date field to trigger a campaign: select the date field in a contact-field condition, then select `date` as the operator; in the **Anniversary** option only day and month values can be entered
- **Documented gotcha 1:** conditions evaluate immediately — contacts do not wait for a condition to become true
- **Documented gotcha 2:** the recommended pattern is a segment filtered on a date field equal to `TODAY`, driving the campaign — but the docs state this **does not work** for the Anniversary option
- **Documented gotcha 3:** a contact passes through a campaign only once, even if the date value later changes — the key constraint for yearly birthday sends
- Segment date formulas: `birthday`, `anniversary`, `birthday -7 days`, `anniversary -1 month`, plus relative formats (`+1 day`, `-2 weeks`, `3 years ago`)

**Hands-on exercise**
Create a birthday date custom field, build a date-based segment using an anniversary formula, drive a greeting campaign from it, and document how the "passes through once" constraint is handled for annual repetition.

**Official references**

*No worked example exists; the mechanics are fully documented.*

- [Using a custom date field to trigger a Campaign](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html#using-a-custom-date-field-to-trigger-a-campaign) — T1
- [Managing Segments — Using Date Filters](https://docs.mautic.org/en/6.0/segments/manage_segments.html#using-date-filters) · [Date options](https://docs.mautic.org/en/6.0/segments/manage_segments.html#date-options) — T1
- [How to create a date-based segment in Mautic](https://kb.mautic.org/article/how-to-create-a-date-based-segment-in-mautic.html) — **T3, includes the birthday case explicitly**
- [Manage Custom Fields](https://docs.mautic.org/en/6.0/contacts/custom_fields.html) — T1

---

#### Module 37 — Feedback request campaign

**Learning objectives**
- Trigger a feedback request from a behavioural, score or stage-based signal
- Capture structured responses without a survey tool, using a one-click auto-submitting form
- Route responses back into segmentation and branch on them

**Key concepts to cover**
- **The officially documented two-campaign feedback-loop pattern** (from the lead-scoring article — Mautic has no survey feature, so this is the endorsed approach):
  1. *Request campaign:* signal fires → add to a filterless static "Needs Feedback" segment → wait 3 days → send the request email → remove from campaign → repeat until answered
  2. *Response mechanic:* the email contains one-click buttons linking to a landing page with an **embedded auto-submitting form**, one per response option
  3. *Process campaign:* on submission, remove from "Needs Feedback" and branch by response — each branch taking a different downstream action
- Adapting the pattern for customer-facing feedback: campaign entry from a stage change, point threshold or asset download
- Feedback form design: rating fields, conditional follow-up fields, mapped custom fields
- Form submit actions to tag, score and segment on the response
- Delay-and-remind logic for non-responders
- Frequency rules so a feedback request does not collide with other sends

**Hands-on exercise**
Build a post-purchase feedback campaign: stage-change entry → one-click feedback email → landing page with an auto-submitting form → tag and segment by response → reminder for non-responders after 3 days → branch handling per response.

**Official references**

*No customer-facing worked example exists. The structurally equivalent official example is the sales-feedback loop below — it is directly adaptable.*

- [Lead scoring best practices with Mautic](https://kb.mautic.org/article/lead-scoring-best-practices-with-mautic.html) — **T3, the only official Mautic feedback-request campaign example**; sections *Feedback loops* / *What is a feedback loop?* / *Implementing the feedback loop in Mautic* / *Creating an MQL alert campaign* / *Creating the process feedback campaign*
- [Using the Campaign Builder](https://docs.mautic.org/en/6.0/campaigns/campaign_builder.html) — T1
- [Stages — Moving Contacts between Stages](https://docs.mautic.org/en/6.0/stages/stages.html#moving-contacts-between-stages) — T1
- [Creating conditional Form fields](https://docs.mautic.org/en/6.0/components/forms.html#creating-conditional-form-fields) · [Form actions](https://docs.mautic.org/en/6.0/components/forms.html#form-actions) — T1
- [Tags](https://docs.mautic.org/en/6.0/contacts/tags.html) · [Frequency rules](https://docs.mautic.org/en/6.0/contacts/frequency_rules.html) — T1

---

## 2. Appendix — supporting topics recommended for inclusion

Not on the original outline, but documented in Mautic 6.0 and materially affecting a marketer's competence. Recommend adding as an assessed appendix or as elective modules.

| Topic | Why it matters for a marketer | Official reference |
|---|---|---|
| Reports | The only real route to campaign and channel metrics; scheduled delivery | [Reports](https://docs.mautic.org/en/6.0/reports/reports.html) |
| UTM tags | Attribution of Mautic-driven traffic in analytics | [UTM tags](https://docs.mautic.org/en/6.0/channels/utm_tags.html) |
| SMS text messages | Second channel for marketing messages and campaigns | [SMS Text Messages](https://docs.mautic.org/en/6.0/channels/sms.html) |
| Web notifications | Browser push as a campaign channel | [Web notifications](https://docs.mautic.org/en/6.0/channels/web_notifications.html) |
| Social monitoring | Acquiring contacts from social mentions and hashtags | [Social Monitoring](https://docs.mautic.org/en/6.0/channels/social_monitoring.html) |
| Transactional vs marketing email | Consent, compliance, and the Mautic 5.0 changes | [KB article](https://kb.mautic.org/article/understand-the-difference-transactional-and-marketing-emails-in-mautic.html) |
| Campaign export/import | Sharing campaigns between instances — **Mautic 7.0+ only** | [Exporting](https://docs.mautic.org/en/7.0/campaigns/exporting_campaigns.html) · [Importing](https://docs.mautic.org/en/7.0/campaigns/importing_campaigns.html) |

---

## 3. Remaining documentation gaps

After a full sweep of every official Mautic property, **most gaps in v1.0 of this document are now closed** by Knowledgebase articles, cross-version doc pages, or case studies. What follows is what genuinely has no official reference.

### Closed — alternative sources found

| Topic | Original problem | Resolution |
|---|---|---|
| UI walkthrough | No UI page in 6.0 docs | [KB: Getting started with Mautic](https://kb.mautic.org/article/getting-started-with-mautic.html) — full guided tour |
| Landing pages | 6.0 page is an empty stub | KB *Getting started* §2 (build walkthrough) + [6.0 Builder](https://docs.mautic.org/en/6.0/builders/email_landing_page.html) + [7.1 drafts/preview](https://docs.mautic.org/en/7.1/components/landing_pages.html) + [KB Publish/Unpublish](https://kb.mautic.org/article/explaining-the-publish-unpublish-feature.html) |
| Landing page preview/publish | Not documented in 6.0 | 7.1 drafts/preview page + KB Publish/Unpublish article |
| Email A/B testing | No heading in 6.0 docs | [KB: How to create an A/B test for emails](https://kb.mautic.org/article/how-to-create-an-a-b-test-for-emails-in-mautic.html) — full procedure |
| Email scheduling/sending | No heading in 6.0 docs | [KB: How to send an Email at a scheduled time](https://kb.mautic.org/article/how-to-send-an-email-at-a-scheduled-time.html) + [broadcast cron anchor](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#send-scheduled-broadcasts-segment-emails-cron-job) |
| Tracking script depth | 6.0 page is 4 paragraphs | [manage_contacts.html#contact-tracking](https://docs.mautic.org/en/6.0/contacts/manage_contacts.html#contact-tracking) — 15 anchors of real depth |
| Welcome series campaign | No docs example | Two KB worked examples + a mautic.org blog walkthrough |
| Event promotion campaign | No official reference | [Kendris event case study](https://mautic.org/case-study/streamlining-event-communication-with-progressive-profiling-for-a-trust-company/) — narrative, not a tutorial |
| Feedback request campaign | No official reference | [KB: Lead scoring best practices](https://kb.mautic.org/article/lead-scoring-best-practices-with-mautic.html) — the feedback-loop campaign pair, structurally adaptable |
| Segment rebuild/cron | No anchor on segments page | [cron_jobs.html#segment-cron-jobs](https://docs.mautic.org/en/6.0/configuration/cron_jobs.html#segment-cron-jobs) |

### Still open — no official reference exists anywhere

| # | Topic | Status | Recommended handling |
|---|---|---|---|
| 1 | **Landing page A/B testing** | The feature is confirmed to exist by [mautic.org/features/landing-pages-and-forms](https://mautic.org/features/landing-pages-and-forms/) ("pages can be A/B tested"), but **no procedural documentation exists on any Mautic property** | Do not assess as a linked topic. Either drop from exam scope, or author material and flag it as undocumented. The email A/B procedure is a close conceptual analogue. |
| 2 | **In-email dynamic content** | [mautic.org/features/email-marketing](https://mautic.org/features/email-marketing/) confirms "Dynamic Content to replace entire sections of your emails based on fully configurable filters", but **no how-to exists**. The Dynamic Web Content docs cover website slots only. | Teach website DWC (Module 20) as documented; treat in-email dynamic content as unassessed until documentation exists. |
| 3 | **Reading campaign statistics** | `managing_campaigns.html` is a screen tour with no interpretive guidance; no official page explains how to read campaign performance | Author interpretive material; anchor to Reports (Campaign Events data source) |
| 4 | **Campaign export/import in 6.x** | Genuinely absent — the pages 404 in 6.0. Confirmed shipped in **7.0** | Exclude from a 6.x exam; note as a 7.x forward-looking item |
| 5 | **Campaign template library** | Does not exist. The Campaign Library initiative (NLnet/EC funded) completed Phase 1 in Mautic 7.0 and Phase 2 targets Mautic 8.0; **no templates published yet** | Monitor [the initiative](https://community.mautic.org/assemblies/campaign-library) for a future curriculum revision |
| 6 | **Re-engagement / win-back campaigns** | No official example (noted for completeness — not on the original outline) | Out of scope |
| 7 | **Time-of-day event reminders** | Mautic cannot natively segment by time-of-day; the documented workarounds are user-generated forum content | Teach date-level reminders only; state the constraint |

---

## 4. Preparation recommendations

- Review the [Mautic 6.0 documentation](https://docs.mautic.org/en/6.0/) thoroughly, module by module
- Work through the [Mautic Knowledgebase](https://kb.mautic.org/) — its 43 articles carry several topics the product docs do not
- Complete every hands-on exercise on a live Mautic 6.x instance with cron jobs running
- Participate in the [Mautic Community](https://community.mautic.org/) and the [community forum](https://forum.mautic.org/)
- Build at least two complete campaigns end to end before sitting the exam

---

