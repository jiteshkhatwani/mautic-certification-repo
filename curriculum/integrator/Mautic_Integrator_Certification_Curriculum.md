# Mautic Integrator Certification — Curriculum

**Track:** Integrator
**Platform baseline:** Mautic 6.x (documentation reference: `https://docs.mautic.org/en/6.0/`)
**Version:** 1.0
**Prepared by:** Axelerant
**Last reviewed:** 31 August 2026

---

## 1. Program description

The Mautic Integrator Certification validates that a candidate can **install, configure, integrate, secure, operate and upgrade a production Mautic instance**. Where the Marketer track certifies use of Mautic's features, the Integrator track certifies the engineering discipline that keeps those features running: the server and database beneath Mautic, the command line and cron layer that drives it, the Composer/Git workflow that ships it, and the plugin, webhook and REST API surfaces that connect it to the rest of a business's stack.

An Integrator is not expected to write core Mautic PHP (that is the Developer track). An Integrator **is** expected to read code, configure and troubleshoot at the file and CLI level, wire Mautic to external systems, and make safe operational decisions under production constraints.

---

## 2. Target audience

- Technical implementers and solution engineers deploying Mautic for clients
- DevOps / systems engineers responsible for a Mautic instance
- Agency technical leads bridging marketing requirements and infrastructure
- Marketing-operations engineers who own integrations, deliverability and data flow

---

## 3. Prerequisites

Candidates should already be able to:

1. Operate a Linux server over SSH and use a shell confidently (`cd`, `ls`, `find`, `chmod`, `chown`, `scp`, `tar`, pipes and redirection).
2. Read and edit PHP configuration arrays and understand basic PHP syntax; recognise Symfony as the framework Mautic is built on.
3. Use Git at the level of clone, branch, commit, rebase, push, and open a pull request.
4. Read HTML and CSS, and read (not necessarily author) JavaScript.
5. Administer a MySQL or MariaDB database — create databases and users, take and restore dumps, run `SHOW`/`SELECT` queries.
6. Hold, or be able to demonstrate the knowledge covered by, the **Mautic Marketer Certification** — the Integrator exam assumes fluency in Mautic's core objects (contacts, segments, campaigns, emails, forms, landing pages, points, stages).

---

## 4. Certification requirements

| Item | Value |
|---|---|
| Question format | Multiple choice, four options, one correct answer |
| Number of questions | 150 |
| Duration | 180 minutes |
| Pass mark | 70% (105 of 150) |
| Delivery | Proctored online, closed book |
| Platform version examined | Mautic 6.x |
| Validity | 24 months from date of award |
| Recertification | Re-sit the current exam version, or complete an approved delta assessment when a new Mautic major release becomes the certification baseline |

### Domain weighting

| # | Module | Questions | Weight |
|---|---|---|---|
| 1 | Open Source, the Mautic Project & the Release Cycle | 8 | 5.3% |
| 2 | Git, GitHub, Contribution & Translation | 10 | 6.7% |
| 3 | Web Server, PHP/Symfony & Shell Fundamentals | 8 | 5.3% |
| 4 | Database Server Basics & the Mautic Data Model | 8 | 5.3% |
| 5 | Installing Mautic without Composer | 9 | 6.0% |
| 6 | Composer, Packagist & the Mautic Marketplace | 10 | 6.7% |
| 7 | Local Development with DDEV | 7 | 4.7% |
| 8 | Mautic Configuration — UI and `local.php` | 13 | 8.7% |
| 9 | Customizing Mautic & Configuration Best Practices | 9 | 6.0% |
| 10 | Cron Jobs & Console Commands | 13 | 8.7% |
| 11 | Updating Mautic, Backup & Restore | 9 | 6.0% |
| 12 | Deployment & Preparing Mautic for Production | 8 | 5.3% |
| 13 | Secure Setup & Maintenance | 8 | 5.3% |
| 14 | Themes, Email Templating, MJML, CSS & JavaScript | 10 | 6.7% |
| 15 | Email Infrastructure, Service Providers & Deliverability | 9 | 6.0% |
| 16 | Integrations — Plugins, Webhooks & the REST API | 11 | 7.3% |
| | **Total** | **150** | **100%** |

---

## 5. Reference policy

Every reference in this curriculum was individually loaded and verified against an official Mautic-owned source before being cited. Accepted domains:

`docs.mautic.org` · `devdocs.mautic.org` · `kb.mautic.org` · `contribute.mautic.org` · `mautic.org` · `github.com/mautic/*`

Three qualifications the candidate and the trainer must both understand:

- **`devdocs.mautic.org` is the developer documentation.** `developer.mautic.org` now issues a 302 redirect to it. `developer.mautic.org/en/6.0/` returns 404 — do not cite that host.
- **Some Mautic 6.0 pages are empty stubs or stale.** They are listed in §7. A stub is never a valid teaching source.
- **Where a topic has no official Mautic reference at all**, the module says so explicitly with the marker **`NO OFFICIAL MAUTIC REFERENCE`**. Trainers must supply first-party vendor material (for example MDN for CSS/JavaScript, mjml.io for MJML, the Postman docs for Postman) and label it as external.

---

## 6. Modules

### Module 1 — Open Source, the Mautic Project & the Release Cycle

**Learning objectives**

1. State Mautic's licence and explain what GPL v3 permits and requires.
2. Describe the Mautic Community's governance structure and its teams.
3. Explain Mautic's time-based release strategy and its alignment to Symfony.
4. Identify which release in a series is the LTS and calculate a release's support window.
5. Distinguish active support, security support and Extended Long Term Support (ELTS).
6. Choose an appropriate target version for a new client build given a support horizon.

**Key content**

- Mautic was created by DB Hurley and launched in 2014 as an Open Source project **under the GPL v3 licence**.
- Governance Model v2 defines five teams: **Community Team, Education Team, Legal & Finance Team, Marketing Team, Product Team**. Each has an elected Lead and Assistant Lead. A **Community Council** of seven elected representatives is the operational governing body; the **General Assembly** meets annually.
- Decision timeframes: trivial decisions need no vote; non-trivial decisions require a minimum of **36 hours** of discussion; significant decisions require **two weeks or more**. Lazy consensus is the default method.
- Release strategy is **time based** — whatever is ready, tested, documented and merged on release day ships. Major releases follow a **24-month cycle aligned with Symfony's release cycle**.
- The **`.3` release in each series is the LTS**. From the 7.x series onward an LTS carries **12 months active support + 12 months security support = 24 months**.
- Mautic **6.0 is a bridge release** with a combined support window of 21 months. Per `mautic.org/releases/`, 6.0 is marked LTS = Yes, PHP 8.1–8.3, active support to 26 January 2026 and security support to 30 September 2026.
- **ELTS** is a paid, per-instance annual subscription launched Q1 2025 that back-ports security fixes for two additional years, covering CVEs in Mautic core and officially supported plugins.
- Mautic is a **CVE Numbering Authority (CNA) under MITRE** for anything in the Mautic namespace.

**References**

- https://contribute.mautic.org/en/latest/about/about.html
- https://contribute.mautic.org/en/latest/governance/governance_model_v2.html
- https://mautic.org/releases/
- https://mautic.org/blog/introducing-mautics-new-release-strategy-long-term-support-elts/
- https://mautic.org/extended-long-term-support-elts/
- https://mautic.org/security
- https://github.com/mautic/mautic

> **Documentation gap:** there is **no release-cycle, versioning or LTS page anywhere inside `docs.mautic.org/en/6.0/`**. This policy exists only on `mautic.org`. Note also a contradiction between `mautic.org/releases/` (which shows an ELTS date for 6.0) and the ELTS page (which states 6.0 has no ELTS offering because it is a bridge release). Do not teach a definitive answer on Mautic 6 ELTS.

---

### Module 2 — Git, GitHub, Contribution & Translation

**Learning objectives**

1. Navigate the Mautic GitHub organisation and identify the repository for a given purpose.
2. Fork, clone and branch correctly against Mautic's branching strategy.
3. Prepare a pull request that meets Mautic's coding-standard, test and documentation requirements.
4. Rebase a branch against upstream and force-push safely.
5. Explain Mautic's tiered code-review and merge requirements.
6. Test a pull request in a cloud environment without a local install.
7. Contribute and consume Mautic translations.

**Key content**

*Repositories* — `mautic/mautic` (core; default branch **7.x**, with `6.x`, `5.2` and other release branches), `mautic/recommended-project` (Composer template), `mautic/api-library` (official PHP API client). User documentation lives at `docs.mautic.org`, developer documentation at `devdocs.mautic.org`.

*Branching strategy* — all pull requests initially target the **`c.x` branch** (the next major, e.g. `6.x`). Bug fixes for a current release target the `a.b` branch (e.g. `6.0`); features and enhancements for a current release target the `a.x` branch (e.g. `6.x`). **Breaking changes may only merge to a major-version branch.** Forks must go to a **personal account, never an organisation** — an org fork prevents Mautic's maintainers from working with the pull request.

```
git clone https://github.com/USERNAME/mautic.git
git checkout -b BRANCH_NAME 6.x
# for a fix against a specific release
git checkout -t origin/6.0
git checkout -b BRANCH_NAME 6.0
```

*Standards and tests* — Mautic follows **Symfony's Coding Standard** through a pre-commit git hook running **php-cs-fixer**, installed automatically by `composer install` / `composer update`. **Unit tests are mandatory**: "The Core Team won't merge PRs without these tests." Tooling: **PHPUnit** (unit), **Codeception with Selenium** (end-to-end), **PHPStan** (static analysis).

```
bin/phpunit --bootstrap vendor/autoload.php --configuration app/phpunit.xml.dist
bin/codecept build
bin/codecept run acceptance
```

*Rebasing* — `git fetch upstream` → `git merge upstream/6.x` → `git rebase 6.x` → `git push --force origin BRANCH_NAME`.

*Code governance tiers*

| Tier | Change type | Code review | Community testing | Extra |
|---|---|---|---|---|
| 1 | Small changes | 1 Core Team member | ≥1 community member outside the submitter's organisation | — |
| 2 | Minor features | 1 Core Team member | ≥1 independent tester | Full unit test coverage + documentation |
| 3 | Major changes | 1–2 Core Team members | ≥2 community members from different organisations | **2-week community review period**, then a Product Team vote |

Roles: **Core Team** (Release Leaders, Core Committers, Maintainers), **Product Team** (decides which PRs merge), **Triage Team** (daily/weekly issue and PR review).

*Testing a PR without a local install* — the repository ships a **`.gitpod.yml`** on the `6.x` branch, configured with DDEV, prebuilds for pull requests including forks, and the main web port 8080 exposed publicly. Mautic's Knowledgebase documents the Gitpod route (install the Gitpod browser extension, open the PR, click the green **Gitpod** button; log in with `admin`; load sample data with `ddev exec bin/console d:f:l` — which purges the database and must never be run in production). The Community Handbook's Tester page documents the **GitHub Codespaces** route instead: open the PR → Code → Codespaces → create a codespace on the branch → wait for `postCreateCommand` → `ddev start` → open the forwarded port → log in with `admin` / `Maut1cR0cks!`.

*Translation* — Mautic translations are crowdsourced on **Transifex**, and **a daily process generates the language packs from Transifex**. To contribute: create a Transifex account, request to join the Mautic project, and join the `#translations` Slack channel. To force a language pack refresh on an instance: delete the language folder inside the `translations` directory, then open Configuration and save with that language selected — Mautic re-downloads the latest translations. Default language is set in Configuration; an individual user overrides it under their own Account profile. Translations can be overridden without touching core by creating `translations/overrides/[locale]/messages.ini` (e.g. `mautic.dashboard.menu.index="Banana"`) and running `bin/console cache:clear`.

**References**

- https://contribute.mautic.org/en/latest/contributing/developer.html
- https://contribute.mautic.org/en/latest/governance/code_governance.html
- https://contribute.mautic.org/en/latest/contributing/tester.html
- https://contribute.mautic.org/en/latest/contributing/translator.html
- https://docs.mautic.org/en/6.0/translations/translations.html
- https://github.com/mautic/mautic
- https://github.com/mautic/mautic/blob/6.x/.gitpod.yml
- https://github.com/mautic/recommended-project
- https://github.com/mautic/api-library
- https://kb.mautic.org/article/how-do-i-test-bug-fixes-and-new-features-in-mautic.html

> **Conflict to teach explicitly:** the Knowledgebase documents **Gitpod**; the Community Handbook Tester page documents **GitHub Codespaces**. Both routes exist in the repository. Examine the concept (cloud PR testing on a DDEV-backed environment), not the vendor.
> **Gap:** the Translator handbook page does not document how translations are integrated into releases, review/approval, or deadlines.

---

### Module 3 — Web Server, PHP/Symfony & Shell Fundamentals

**Learning objectives**

1. State Mautic 6's supported web servers, PHP versions and required PHP extensions.
2. Diagnose and correct PHP resource-limit failures.
3. Set correct file ownership and permissions for a Mautic install.
4. Work safely in a shell on a production server and recognise destructive commands.
5. Explain Symfony's role in Mautic and locate the Symfony conventions Mautic inherits.

**Key content**

*Requirements (Mautic 6.0)* — PHP **8.1, 8.2, 8.3**. Required PHP extensions: **`xml`, `mysql`, `imap`, `zip`, `intl`, `curl`, `gd`, `mbstring`, `bcmath`**. From Mautic 5.0 onwards **`npm` is also required**. Web servers: **Apache 2.x** (mod_rewrite needed for SEO URLs), **Nginx 1.0+ (1.8 recommended)**, **Microsoft IIS 7**. **Shared hosting is not recommended** — a VPS or dedicated server is required, and community support is unlikely for shared-hosting installs.

*PHP settings* — `max_execution_time` must be **at least 240 seconds**. Documented error strings and their causes: `The Uploaded file exceeds the upload_max_filesize directive`, `Maximum execution time of 30 seconds exceeded`, `PHP Error: Allowed memory size of <number> bytes exhausted`. Diagnose with `php -i | grep .ini` and `php -i | grep upload_max_filesize`. In the UI: **Settings → System Info → PHP Info**, where **Master value** is the main `php.ini` and **Local value** is an override from `httpd.conf`, `.htaccess` or a directory-level `.ini`. `.htaccess` overrides such as `php_value upload_max_filesize 20M` are documented as "a last resort".

*Apache lifecycle* — `sudo apachectl configtest`, then `sudo systemctl restart apache2` (Ubuntu/Debian) or `sudo systemctl restart httpd` (CentOS/RHEL).

*Permissions and ownership* — the documented reset:

```
find . -type f -not -perm 644 -exec chmod 644 {} +
find . -type d -not -perm 755 -exec chmod 755 {} +
chmod -R g+w var/cache/ var/logs/ app/config/
chmod -R g+w media/files/ media/images/ translations/
rm -rf var/cache/*
ps aux | grep apache2
groups apache_user
sudo chown -R apache_user:apache_group /path/to/mautic
```

Common root causes of permission failures: uploading files as a different user than the web-server user, insufficient permissions, or running an update as the wrong user. **Note:** the `app/config/` path in that snippet is pre-Mautic-5; Mautic 5+ uses `config/local.php`.

*Shell risk awareness* — `rm -rf var/cache/*` is documented and safe; `mautic:maintenance:cleanup` **permanently deletes data** and the docs require verified database backups before use; `ddev exec bin/console d:f:l` (fixtures load) **purges the database** and must never run in production. Application logs live in `var/logs`; Ubuntu Apache errors in `/var/log/apache2/error.log`; cron output should be redirected with `>>/path/to/somefile.log 2>&1`, and the file's modification time tells you when the job last ran.

*Symfony* — Mautic is built on **Symfony and Doctrine**. Mautic follows Symfony's environment conventions, uses the Symfony **Console** component (`bin/console`), **Symfony Mailer** for all email transports since Mautic 5, and **Symfony Messenger** for queueing. Plugins are Symfony bundles.

**References**

- https://mautic.org/mautic-requirements/
- https://docs.mautic.org/en/6.0/troubleshooting/working_with_resource_limits.html
- https://docs.mautic.org/en/6.0/troubleshooting/file_ownership_permissions.html
- https://docs.mautic.org/en/6.0/getting_started/how_to_install_mautic.html
- https://devdocs.mautic.org/en/6.0/development-environment/getting_started.html

> **NO OFFICIAL MAUTIC REFERENCE** for: web-server configuration examples (no vhost, no Nginx server block, no `.htaccess` contents), PHP-FPM tuning, or shell scripting as a discipline. Trainers must supply external first-party material and label it as such.
> **Conflict:** the contributor handbook lists a different PHP extension set (`zip, xml, mcrypt, imap, mailparse`) than the requirements page. **The requirements page is authoritative.** The handbook is also the only official source for a memory figure: "minimal 256 MB for testing and 512 MB or more for production".

---

### Module 4 — Database Server Basics & the Mautic Data Model

**Learning objectives**

1. State the supported database engines and minimum versions for Mautic 6.
2. Configure Mautic's database connection parameters, including a table prefix.
3. Run Doctrine schema and migration commands safely.
4. Identify Mautic's core reporting tables and explain why table names must never be hard-coded.
5. Explain how Mautic defines its schema through Doctrine and where the 191-character limit comes from.

**Key content**

- **MySQL 5.7 minimum (InnoDB support required)** or **MariaDB 10.2 or higher**. No upper bound is published. The official DDEV configuration ships **MariaDB 10.3**.
- Connection parameters: `db_driver` (default `pdo_mysql`), `db_host` (default `127.0.0.1`), `db_port` (default `3306`), `db_name`, `db_user`, `db_password`, `db_table_prefix`, plus `db_host_ro` for a read-only replica. The web installer also offers **"Backup existing tables?"** (on by default, `--db_backup_tables`, default `true`) and a **backup table prefix** (`--db_backup_prefix`, default `bak_`).
- The only official MySQL tuning statement Mautic publishes, from the contributor handbook:

```
SET GLOBAL innodb_default_row_format=DYNAMIC;
SET GLOBAL sql_mode=(SELECT REPLACE(@@sql_mode,'ONLY_FULL_GROUP_BY',''));
```

- Schema management:

```
php bin/console doctrine:migration:status
php bin/console doctrine:migration:migrate
php bin/console doctrine:schema:update --dump-sql   # prints SQL, executes nothing
php bin/console doctrine:schema:update --force
```

  The in-app schema check endpoint is **`example.com/s/update/schema`**.
- **Data model.** Mautic uses **Doctrine ORM** to define its schema; entities live in an `Entity/` directory. Mautic's **`ClassMetadataBuilder`** decorates Doctrine's builder and **automatically caps string and indexed field length at 191 characters** for UTF8MB4 compatibility. Helper methods include `addId()`, `addBigIntIdField()`, `addUuid()`, `addContact()` (many-to-one to the **`Lead`** entity), `addCategory()`, `addDateAdded()`, `addPublishDates()`, `addIpAddress()`.
- **Table prefixes are configurable per install.** Migrations must use `concatPrefix()` and the `$tablePrefix` property rather than hard-coded table names — this is the single most consequential data-model fact for an integrator writing SQL against a client instance.
- The authoritative published list of table names is the **`GET /stats`** API's `availableTables`, which exposes the reporting/stat tables: `companies_leads`, `lead_categories`, `lead_companies_change_log`, `lead_devices`, `lead_donotcontact`, `lead_event_log`, `lead_frequencyrules`, `lead_lists_leads`, `lead_points_change_log`, `lead_stages_change_log`, `lead_utmtags`, `asset_downloads`, `campaign_leads`, `campaign_lead_event_log`, `email_stats`, `email_stats_devices`, `email_stat_replies`, `form_submissions`, `page_hits`, `page_redirects`, `video_hits`, `channel_url_trackables`, `point_lead_action_log`, `point_lead_event_log`, `stage_lead_action_log`, `dynamic_content_stats`, `dynamic_content_lead_data`, `push_notification_stats`, `sms_message_stats`, `audit_log`, `ip_addresses`, `webhook_logs`.
- Symfony Messenger's Doctrine transport stores queued messages in **`messenger_messages`**.

**References**

- https://mautic.org/mautic-requirements/
- https://devdocs.mautic.org/en/6.0/plugins/database.html
- https://devdocs.mautic.org/en/6.0/rest_api/stats.html
- https://docs.mautic.org/en/6.0/troubleshooting/troubleshooting.html
- https://contribute.mautic.org/en/latest/contributing/developer.html
- https://docs.mautic.org/en/6.0/getting_started/how_to_install_mautic.html

> **NO OFFICIAL MAUTIC REFERENCE** for: an entity-relationship diagram, a table-by-table schema reference covering the core `leads` / `lead_fields` / `campaigns` / `emails` / `pages` / `forms` tables, required database user privileges, charset/collation guidance, index tuning, `OPTIMIZE TABLE` guidance, or any MySQL sizing parameter such as `innodb_buffer_pool_size`. Teach the *mechanics* Mautic documents; treat the physical schema as something to be read from a live instance.

---

### Module 5 — Installing Mautic without Composer

**Learning objectives**

1. Run the pre-flight environment checks and interpret their colour coding.
2. Complete a zip/web-installer installation end to end.
3. Complete a fully non-interactive CLI installation.
4. Pre-seed installation parameters through `local.php`.
5. Decide between SMTP and API-based sending at install time.

**Key content**

- Mautic frames installation as three steps: **integrate the database server, create an administrator account, set up the email server**.
- Zip route: download from `mautic.org/download` → upload to the web server → unzip into the hosting directory → ensure the web server has permissions on the unzipped files → browse to the instance URL.
- Web installer stage order: **Environment checks → Database → Administrator account → Email settings → Log in**. Pre-flight colour coding: **red = errors that must be resolved, orange = warnings/recommendations, green = success**.
- Database Setup fields: Driver, Host, Name, Username; optional Port, Table Prefix, Password, backup-table prefix. **"Backup existing tables?" is ON by default and should be switched OFF for a new installation.**
- CLI install:

```
path/to/php bin/console mautic:install https://m.example.com
path/to/php bin/console mautic:install --help
```

  Documented flags include `--db_driver` (default `pdo_mysql`), `--db_host`, `--db_port`, `--db_name`, `--db_user`, `--db_password`, `--db_table_prefix`, `--db_backup_tables` (default `true`), `--db_backup_prefix` (default `bak_`), `--admin_firstname`, `--admin_lastname`, `--admin_username`, `--admin_email`, `--admin_password`, `--mailer_from_name`, `--mailer_from_email`, `--mailer_transport`, `--mailer_host`, `--mailer_port`, `--mailer_user`, `--mailer_password`, `--mailer_encryption` (`null|tls|ssl`), `--mailer_auth_mode` (`null|plain|login|cram-md5`), `--mailer_spool_type` (`file|memory`), `--mailer_spool_path`.
- CLI installer stage output: `0 - Checking installation requirements...` → `Ready to Install!` → `1 - Creating database...` → `1.1 - Creating schema...` → `1.2 - Loading fixtures...` → `2 - Creating admin user...` → `3 - Email configuration and final steps...` → `Install complete`.
- Pre-seeding via a `local.php` `$parameters = array(...)` block is supported, with the documented caveat: **do not set `db_driver` or `mailer_from_name`**, because their presence is how Mautic decides it is already installed.
- **Mautic 5.1 and later require a complex admin password.** The documentation's worked example throughout is `Maut1cR0cks!`.
- Email step: choose a mailer transport, or **Other SMTP Server** if the provider is not listed. The docs state **"API-based sending is significantly faster than SMTP"**, and offer the option to queue emails and send via cron rather than immediately.
- Securing the install with an **SSL certificate (https)** is recommended.

**References**

- https://docs.mautic.org/en/6.0/getting_started/how_to_install_mautic.html
- https://mautic.org/mautic-requirements/
- https://mautic.org/download
- https://docs.mautic.org/en/6.0/configuration/command_line_interface.html

> **Documentation defect to flag:** `mautic:install` is **absent from the Mautic 6.0 CLI command reference** (only `mautic:install:data` appears there). The command exists and is documented on the installation page. Also note the installer prints an **unresolved placeholder** `%min_memory_limit%` in its memory warning, so no official minimum memory figure is published there.

---

### Module 6 — Composer, Packagist & the Mautic Marketplace

**Learning objectives**

1. Explain what Composer is, how Packagist relates to it, and what `composer.json` vs `composer.lock` do.
2. Create a new Mautic project from the Recommended Project template.
3. Explain the Recommended Project's directory contract and configure a web server for it.
4. Change the web root from `docroot` to `public` for a new and an existing project.
5. Convert an existing zip install to a Composer-managed install.
6. Manage plugins through the Mautic Marketplace and understand its Packagist requirements.
7. Apply patches and scaffolding correctly.

**Key content**

- Composer installation has been possible **since Mautic 4.0**. Per the update documentation: **"From Mautic 6, the default way to install, update and manage Mautic changes to Composer."**
- Project creation, as printed in the 6.0 docs:

```
composer create-project mautic/recommended-project:^5 some-dir --no-interaction
```

- **The Recommended Project contract:** Mautic is installed into **`docroot`**; the autoloader is the generated Composer autoloader at **`vendor/autoload.php`** (not `docroot/vendor/autoload.php`); packages of type **`mautic-plugin`** land in `docroot/plugins/`; packages of type **`mautic-theme`** land in `docroot/themes/`; `docroot/media` is created; environment variables come from your `.env` file (see `.env.example`). **The web server document root must be `<project>/docroot`** or errors follow.
- Scaffolding: the **`mautic/core-composer-scaffold`** plugin writes files such as **`index.php`** and **`.htaccess`** into `docroot/`. Automate it by registering `"@composer mautic:scaffold"` under both `post-install-cmd` and `post-update-cmd` in `composer.json`.
- Patching: use the **`composer-patches`** plugin, declaring patches under `"extra": { "patches": { "mautic/foobar": { "Description": "path-or-url.patch" } } }`.
- Adding dependencies: `composer require mautic/mautic/helloworld-bundle`.
- Changing `docroot` → `public`: for a **new** project use `--no-install`, find/replace `docroot/` with `public/` in `composer.json`, then `composer install`. For an **existing** project `mv docroot public`, find/replace, then `composer update --lock` "to ensure the autoloader is aware of the changed folder", and update the web-server configuration.
- **Switching a zip install to Composer** (minimum version required: **Mautic 4.0.0**; the database is not touched, only the codebase): create the new project alongside; copy `app/config/local.php` → `docroot/app/config/local.php`, the whole `plugins` directory, `app/media/files`, `app/media/images`, `app/media/dashboards`, custom `themes`, and `translations`; swap the directories; repoint the web server to `<project>/docroot`; then enable the "fully manage Mautic with Composer" switch in global settings — **which also enables the Mautic Marketplace**.
- **Marketplace.** From **Mautic 4.2** a configuration setting declares that the instance uses Composer, which allows installing, updating and removing plugins from the Marketplace. **Mautic 4.0.0** shipped a read-only Marketplace; **4.2.0** added install/remove. The Marketplace **uses Packagist and Composer v2 under the hood**. CLI: `bin/console mautic:marketplace:list`. Documented caveat: **"The current Marketplace version doesn't verify Mautic version compatibility of Plugins yet."**
- **Listing a plugin on the Marketplace:** `composer.json` must declare `"type": "mautic-plugin"` — "The Marketplace is filtering PHP packages by this tag. It's required to show up in the Marketplace." Recommended keywords `mautic`, `plugin`, `integration`; `extra.install-directory-name` must match the bundle namespace for PSR-4 autoloading; require `mautic/core-lib` at the tested version; publish to Packagist and then apply for **allow-list approval** while the Marketplace is in beta. Legacy plugins must drop any `mautic/composer-plugin` dependency.
- The Marketplace **is not compatible with the zip install method** — this is the stated rationale for switching.

**References**

- https://docs.mautic.org/en/6.0/getting_started/how_to_install_mautic.html
- https://docs.mautic.org/en/6.0/getting_started/switching_composer.html
- https://docs.mautic.org/en/6.0/marketplace/marketplace.html
- https://devdocs.mautic.org/en/6.0/marketplace/getting_started.html
- https://devdocs.mautic.org/en/6.0/marketplace/listing.html
- https://github.com/mautic/recommended-project

> **Stale content to flag in training:** the Mautic **6.0** documentation and the `recommended-project` **6.x** README both still print the constraint `mautic/recommended-project:^5` (the README additionally claims a PHP 7.4 minimum). Teach the documented string, and teach candidates to reason that a 6.x install needs a 6.x constraint. Do not build an exam question that requires guessing an undocumented `^6`.

---

### Module 7 — Local Development with DDEV

**Learning objectives**

1. Explain what DDEV provides and why Mautic standardises on it.
2. Start a Mautic instance with DDEV from a clone of the repository.
3. Identify the services DDEV provisions and how to reach them.
4. Run Mautic console commands and test suites inside DDEV.
5. Read `.ddev/config.yaml` and explain what it pins.

**Key content**

- Prerequisites: **DDEV and Docker (or Colima)**. Two commands are all that is documented:

```
git clone https://github.com/mautic/mautic.git
cd mautic && ddev start
```

- `ddev start` spins up an instance including **MailHog, PHPMyAdmin and Redis Commander**, by default at **`https://mautic.ddev.site`**, and offers to run the Composer install and CLI install for you. Default credentials **`admin` / `Maut1cR0cks!`** (`sales` / `Maut1cR0cks!` also exists). Versions prior to 5.1 used the password `mautic`.
- The repository's `.ddev/config.yaml` on `6.x` pins **`php_version: "8.3"`**, **`webserver_type: apache-fpm`**, **MariaDB 10.3**, **`composer_version: "2"`**, `upload_dirs: media/files, media/images`, and adds the PHP `imap` extension via `webimage_extra_packages`.
- The bootstrap script `.ddev/mautic-setup.sh` runs `composer install`, copies `.ddev/local.config.php.dist` to **`./config/local.php`** (note the Mautic 5+ path), copies `.env` templates, then runs `php bin/console mautic:install`, `php bin/console cache:warmup --no-interaction --env=dev` and `php bin/console mautic:plugins:reload`. It exposes PHPMyAdmin on **:8037** and MailHog on **:8026**.
- Working inside DDEV:

```
ddev exec bin/console mautic:segments:update
ddev exec composer test        # PHPUnit
ddev exec composer e2e-test    # end-to-end suite
ddev stop
```

- Useful generic DDEV verbs documented by Mautic: `ddev config`, `ddev start`, `ddev stop`, `ddev restart`, `ddev ssh`, `ddev exec`, `ddev describe`, `ddev exec enable_xdebug` / `disable_xdebug`.

**References**

- https://devdocs.mautic.org/en/6.0/development-environment/how_to_install_with_ddev.html
- https://docs.mautic.org/en/6.0/getting_started/how_to_install_mautic.html
- https://contribute.mautic.org/en/latest/contributing/developer.html
- https://github.com/mautic/mautic/blob/6.x/.ddev/config.yaml
- https://mautic.org/blog/local-mautic-development-with-ddev/

> **Stale/conflicting content:** the DDEV blog post documents PHP 7.3, MailHog on :8025 and PHPMyAdmin on :8036 — superseded by the repository configuration. The contributor handbook says the host is `https://mautic.ddev`; the install page and DDEV's own default say **`https://mautic.ddev.site`**. Use the repository as ground truth.

---

### Module 8 — Mautic Configuration: UI and `local.php`

**Learning objectives**

1. Navigate every tab of Settings → Configuration and state what it controls.
2. Locate the local configuration file for Mautic 6 and explain the path change from earlier versions.
3. Set core parameters — URLs, paths, trusted hosts and proxies, CORS, cookies, locale, date formats.
4. Configure Mautic behind a reverse proxy or SSL-terminating load balancer.
5. Override any parameter through an environment variable.
6. Explain Mautic's `.env` precedence rules and production compilation.

**Key content**

*Configuration tabs, in the order the docs present them:* System settings, Theme settings, API settings, Asset settings, Campaign settings, Email settings, Form settings, Contact settings, Segment settings, Company settings, Queue settings, Notification settings, Landing Page settings, Tracking settings, Report settings, Text message settings, User/Authentication settings, Webhook settings, Social settings.

*The local configuration file.* In Mautic 6 `app/config/paths.php` defines `'local_config' => '%kernel.project_dir%/config/local.php'` — i.e. **`config/local.php` at the project root**. Prior to Mautic 5.0 it was `app/config/local.php`. Paths overridable in `config/paths_local.php`: `themes`, `assets` (`app/assets`), `media`, `asset_prefix`, `plugins`, `translations`.

*Core parameters and their shipped defaults* (from `app/bundles/CoreBundle/Config/config.php` on `6.x`):

| Parameter | Default |
|---|---|
| `site_url` | `''` |
| `404_page` | `''` |
| `cache_path` | `%kernel.project_dir%/var/cache` |
| `log_path` | `%kernel.project_dir%/var/logs` |
| `max_log_files` | `7` |
| `image_path` | `media/images` |
| `tmp_path` | `%kernel.project_dir%/var/tmp` |
| `theme` | `blank` |
| `db_driver` / `db_host` / `db_port` | `pdo_mysql` / `127.0.0.1` / `3306` |
| `locale` | `en_US` |
| `trusted_hosts` / `trusted_proxies` | `[]` / `[]` |
| `rememberme_lifetime` | `31536000` (365 days) |
| `default_pagelimit` | `30` |
| `default_timezone` | `UTC` |
| `date_format_full` | `F j, Y g:i a T` |
| `ip_lookup_service` | `maxmind_download` |
| `update_stability` | `stable` |
| `cookie_secure` | `true` |
| `cookie_httponly` | `false` |
| `cached_data_timeout` | `10` |
| `cors_restrict_domains` | `true` |
| `cors_valid_domains` | `[]` |
| `headers_sts` | `false` |
| `max_entity_lock_time` | `0` |
| `gdpr_user_purge_threshold` | `1095` |

*UI specifics worth memorising* — **Site URL** is "where Mautic is physically installed"; cron jobs need it to build absolute URLs in emails. **CORS → Restrict Domains** should be set to **Yes** ("strongly recommended"); valid domains are one per line and **must not end in a slash**. **Trusted proxies** are "mandatory when using Mautic behind an SSL terminating proxy" (e.g. `127.0.0.1, 10.0.0.0/8, fc00::/7`); **Trusted hosts** accept regex such as `.*\.?example.com$` and, if left empty, Mautic responds to all hosts. **API settings** default to access-token lifetime **60 minutes** and refresh-token lifetime **14 days**. **Asset settings** advise placing the asset directory **outside the public web root**.

*Environment variables.* Mautic follows Symfony's environment conventions. Load order, later overriding earlier: `.env` → `.env.local` → `.env.$APP_ENV` → `.env.$APP_ENV.local`, and **real environment variables win over `.env` files**. The shipped `.env` contains `APP_ENV=prod` and `APP_DEBUG=0`, with the warning **"DO NOT DEFINE PRODUCTION SECRETS IN THIS FILE NOR IN ANY OTHER COMMITTED FILES."** For production, `composer dump-env prod` compiles the files (requires `symfony/flex >= 1.2`).

*The mapping rule.* `app/config/parameters.php` registers every bundle parameter `foo` as the container parameter `mautic.foo` bound to the environment variable **`MAUTIC_FOO`** — so **any configuration parameter can be set as an uppercase `MAUTIC_`-prefixed environment variable**. Type processors are applied automatically (`bool:`, `intNullable:`, `json:`, `float:`, `nullable:`). Additional direct env vars: `MAUTIC_REQUEST_CONTEXT_HOST`, `MAUTIC_REQUEST_CONTEXT_SCHEME`, `MAUTIC_REQUEST_CONTEXT_BASE_URL`, `MAUTIC_REQUEST_CONTEXT_HTTP_PORT`, `MAUTIC_REQUEST_CONTEXT_HTTPS_PORT`.

*Tokens vs parameters.* `configuration/variables.html` is despite its name a **token reference** (`{contactfield=firstname}`, `{unsubscribe_url}`, `{tracking_pixel}`, `{form=83}`, `{assetlink=25}`, and the pipe-fallback form `{contactfield=firstname|there}`) — not a configuration-parameter reference.

**References**

- https://docs.mautic.org/en/6.0/configuration/settings.html
- https://docs.mautic.org/en/6.0/configuration/variables.html
- https://docs.mautic.org/en/6.0/configuration/maxmind_license.html
- https://docs.mautic.org/en/6.0/configuration/shortener.html
- https://docs.mautic.org/en/6.0/configuration/tracking_script.html
- https://devdocs.mautic.org/en/6.0/development-environment/environments.html
- https://github.com/mautic/mautic/blob/6.x/app/config/paths.php
- https://github.com/mautic/mautic/blob/6.x/app/bundles/CoreBundle/Config/config.php

> **Major documentation gap:** there is **no `local.php` configuration-parameter reference page** in any Mautic-owned documentation site for 6.x. The parameter list must be derived from `github.com/mautic/mautic/blob/6.x/app/bundles/*/Config/config.php`. Trainers should hand candidates a curated parameter table built from those files.
> **Conflicts to teach:** the settings page states the default item limit per page is 10, while the shipped default is `default_pagelimit => 30`. `contacts/custom_fields.html` and the file-permissions page still say `app/config/local.php`, contradicting `paths.php`.

---

### Module 9 — Customizing Mautic & Configuration Best Practices

**Learning objectives**

1. Create and manage custom fields, including background column creation and field-width optimisation.
2. Design a role and permission model and read Mautic's permission notation.
3. Manage users and understand what Mautic does and does not send them.
4. Configure categories, tags, stages, points and point groups correctly.
5. Configure dynamic content and know which slot name it uses.
6. Apply the documented performance-oriented configuration settings.
7. Configure Symfony Messenger queueing and choose a transport.

**Key content**

*Custom fields.* Listing icons: **lock** = core field, cannot be removed; **list** = usable as a segment filter; **asterisk** = mandatory on the contact form; **globe** = publicly updatable via the tracking-pixel URL query. From Mautic 5 the default value cannot be edited for identifier fields (Email, Company, First name, Last name, social profiles, unique identifiers, Company name/Email/website, State, Country, City). Background creation: set `'create_custom_field_in_background' => true` (available since Mautic 3.3) and then run `bin/console mautic:custom-field:create-column` — the docs recommend running it once daily when most of the audience is offline. Since 5.1, `bin/console mautic:fields:analyse -t` analyses and optimises VARCHAR column sizes when approaching the leads-table field limit; `mautic:fields:analyse > path/to/file.csv` exports. Since 5.1, custom countries/regions can be supplied as `countries.json` / `regions.json` in the configured `upload_dir` (default `media/files`).

*Roles and permissions.* **Settings → Roles**. Setting **Full System Access = Yes** creates an administrator and disables per-permission configuration. Permission options are **View, Edit, Create, Delete, Activate, Full**, with **Own**/**Others** scoping and **Manage**; the Users section adds **Specified fields** / **All**. New users default to the **Administrator** role. Since **Mautic 5.1** there is an additional **export** permission within Contact, Forms and Reports permissions. Permission notation is `bundleName:permissionLevel:permission` for core (`user:roles:edit`) and `plugin:bundleName:permissionLevel:permission` for plugins. Bits double — 1, 2, 4, 8, 16, 32, 64, 128, 512, 1024 — and `full` is always the highest bit. Core's shipped extended set is `viewown 2, viewother 4, editown 8, editother 16, create 32, deleteown 64, deleteother 128, publishown 256, publishother 512, full 1024`.

*Users.* **Settings → Users → +New**. Fields include Roles, Signature (only needed with the "Mailer is owner" feature), Username, Email, Password, Time zone, Language. **Passwords must be at least six characters.** Mautic **does not email new users their login information** — credentials must be delivered out of band.

*Categories, tags, stages, points.* Categories are available for **Assets, Campaigns, Emails, Focus Items, Forms, Pages, Points, Social Monitoring and Stages**, with fields type, title, description, alias, colour and availability. Tags do not require pre-creation; segment filter operators are **Includes, Excludes, Empty, Not empty**; search syntax is `tag:tagname`, `!tag:tagname` and `tag:"tag name"`. **Stages**: a contact can only be in **one stage at a time**, and **contacts cannot move backwards to a stage with a lower weight**; movement requires the campaign action *Change Contact's Stage*. **Point groups** each add a new segment filter — and note the documented gotcha that **changing contact group points does not trigger the Contact Points Changed webhook**.

*Dynamic content.* **Components → Dynamic Content**, either campaign-based (using the *Request Dynamic Content* decision and *Push Dynamic Content* action) or filter-based. The template slot is **`<div data-slot="dwc" data-param-slot-name="myslot">`** — the slot type is `dwc`, not `dynamicContent`.

*Documented performance settings.* Campaigns → **Use summary statistics** ("improves performance when viewing a Campaign with thousands of events per day"; requires a cron run to summarise existing data). Contacts → **Automatically import in the background if the CSV has more rows than defined** (set to 0 to always import in the background). Segments → **Show warning if Segment hasn't been rebuilt for X hours**. Webhooks → **Queue Mode** ("improves performance by only adding the event to the queue" and requires a cron command) plus event ordering.

*Queueing (Symfony Messenger).* A fresh instance has **queueing turned off** — the DSN is **`sync://`**. Transports: **Doctrine** (no extra extension, uses table `messenger_messages`), **Redis** (PHP extension ≥ 4.3, Redis server ^5.0), **AMQP** (AMQP extension + RabbitMQ-type service), **Beanstalkd** (`composer require symfony/beanstalkd-messenger`), **Amazon SQS** (`composer require symfony/amazon-sqs-messenger`). Consume with `php bin/console messenger:consume email`, kept alive by **Supervisor or systemd**. Config keys: `messenger_dsn_email`, `messenger_dsn_hit`, `messenger_dsn_failed`, `messenger_retry_strategy_max_retries` (3), `messenger_retry_strategy_delay` (1000 ms), `messenger_retry_strategy_multiplier` (2.0), `messenger_retry_strategy_max_delay` (0). **Messages failing all retries are discarded by default** unless a failure transport is configured.

**References**

- https://docs.mautic.org/en/6.0/contacts/custom_fields.html
- https://docs.mautic.org/en/6.0/users_roles/managing_roles.html
- https://docs.mautic.org/en/6.0/users_roles/managing_users.html
- https://devdocs.mautic.org/en/6.0/plugins/permissions.html
- https://docs.mautic.org/en/6.0/categories/categories-overview.html
- https://docs.mautic.org/en/6.0/contacts/tags.html
- https://docs.mautic.org/en/6.0/stages/stages.html
- https://docs.mautic.org/en/6.0/points/points.html
- https://docs.mautic.org/en/6.0/points/point_groups.html
- https://docs.mautic.org/en/6.0/components/dynamic_web_content.html
- https://docs.mautic.org/en/6.0/configuration/settings.html

> **Stale page — do not teach:** `https://docs.mautic.org/en/6.0/queue/queue.html` documents the **pre-Messenger** architecture (a `queue_protocol` parameter, `rabbitmq_*` / `beanstalkd_*` keys, and the command `mautic:email:send` which no longer exists in Mautic 6). Teach the Queue settings section of `configuration/settings.html` and the `messenger_dsn_*` parameters instead.
> **NO OFFICIAL MAUTIC REFERENCE** for Custom Objects in Mautic 6 core documentation.

---

### Module 10 — Cron Jobs & Console Commands

**Learning objectives**

1. Install the required cron jobs in the correct order with correct staggering.
2. Choose and tune batch limits for segment and campaign processing.
3. Select the correct optional cron jobs for a given feature set.
4. Use the console safely and non-interactively, and capture output.
5. Diagnose cron failures caused by the PHP binary, argv handling or interactivity.
6. Distinguish commands that look similar but do different things.

**Key content**

*Console basics.* Format `command [options] [arguments]`; **you must be in the Mautic root directory**; run `bin/console` to discover the full list. Since Mautic 3 the path is `bin/console` (Mautic 2.x used `app/console`). Global options include `-e, --env=ENV` (default `prod`), `-n, --no-interaction`, `--no-ansi`, `-q, --quiet`, `-v/-vv/-vvv`.

*Required cron jobs and the documented stagger:*

```
0,15,30,45  →  php bin/console mautic:segments:update
5,20,35,50  →  php bin/console mautic:campaigns:update
10,25,40,55 →  php bin/console mautic:campaigns:trigger
```

- `mautic:segments:update` — batches of **300** by default; `--batch-limit=X`; `--max-contacts`. Alias `mautic:segments:rebuild`.
- `mautic:campaigns:update` — batches of **300**; `--batch-limit=X`; `--max-contacts`. Alias of `mautic:campaigns:rebuild`.
- `mautic:campaigns:trigger` — batches of **100**; `--batch-limit=X` controls *events* per batch; the cap flag is **`--max-events`**, not `--max-contacts`. **Since Mautic 5.1 campaigns are triggered newest to oldest.**
- `mautic:messages:send` — processes marketing messages held by frequency rules. Aliases `mautic:campaigns:messagequeue`, `mautic:campaigns:messages`.
- `mautic:custom-field:create-column` — creates the actual column when background field creation is enabled.

*Optional cron jobs.*

| Purpose | Command |
|---|---|
| Process the email queue | `messenger:consume email --time-limit=160` |
| Fetch monitored email (bounces) | `mautic:email:fetch` |
| Social monitoring | `mautic:social:monitoring` |
| Background contact imports | `mautic:import` |
| Scheduled contact exports | `mautic:contacts:scheduled_export` |
| Process queued webhooks | `mautic:webhooks:process` |
| Refresh MaxMind GeoLite2 | `mautic:iplookup:download` |
| Clean up old data | `mautic:maintenance:cleanup --days-old=365 --dry-run` |
| CCPA do-not-sell (weekly, in this order) | `mautic:donotsell:download` then `mautic:max-mind:purge` |
| Send segment email broadcasts | `mautic:broadcasts:send` |
| Scheduled reports | `mautic:reports:scheduler [--report=ID]` |
| Integration sync | `mautic:integration:fetchleads` / `mautic:integration:pushactivity` |
| Reload plugins | `mautic:plugins:reload` |

- **`messenger:consume` must be given at least one of `--memory-limit`, `--limit` or `--time-limit`**, otherwise it starts a long-lived process that never exits.
- `mautic:webhooks:process` supports range mode since 5.1: `--webhook-id=5 --min-id=1000 --max-id=2000`.
- `mautic:maintenance:cleanup` supports `--days-old=X`, `--dry-run` and `--gdpr` (which deletes contacts inactive for **3 years**). The docs warn: **"This permanently deletes data. Be sure to verify database backups before using as appropriate."**
- `mautic:broadcasts:send` flags: `--channel=email`, `--id=X`, `--limit=X` (contacts pulled per database read, **default 100**), `--batch=X` (emails per batch — set to 1000 for providers whose API accepts 1000 per call), and `--min-contact-id` / `--max-contact-id` for **parallel, non-overlapping** execution. The email **must have a published-up date and be currently published**.
- **`--exclude`** prevents re-processing already-processed entities and is available on exactly three commands: `mautic:campaigns:trigger`, `mautic:campaigns:rebuild`, `mautic:segments:update`.
- MaxMind updates its database **the first Tuesday of the month**.
- Integration commands should name the integration: `--integration=Hubspot`.
- `mautic:plugins:reload` has the aliases `mautic:plugins:install` and `mautic:plugins:update` — the same command.

*Commands that are easy to confuse:*

| Command | What it actually does |
|---|---|
| `cache:clear` | Clears the Symfony cache |
| `mautic:cache:clear` | Erases the **10-minute Mautic cache** holding segment counts and dashboard widget data |
| `mautic:campaigns:update` / `:rebuild` | Recalculates campaign membership from segments |
| `mautic:campaigns:trigger` | Fires the timed events for active campaigns |
| `mautic:messages:send` | Sends the **frequency-rule** message queue |
| `messenger:consume email` | Drains the **Symfony Messenger** mail queue |
| `mautic:assets:generate` | Combines and minifies bundle CSS/JS into production files |

*Troubleshooting.* Use `php-cli` where the host aliases `php` in a way that discards console parameters. Enable non-interactive and no-ANSI mode for cron: `mautic:segments:update --no-interaction --no-ansi`. Redirect output: `>>/path/to/somefile.log 2>&1`. If you see `Warning: Invalid argument supplied for foreach() ... ArgvInput.php:287`, use `php-cli` or `php -d register_argc_argv=On`.

**References**

- https://docs.mautic.org/en/6.0/configuration/cron_jobs.html
- https://docs.mautic.org/en/6.0/configuration/command_line_interface.html
- https://docs.mautic.org/en/6.0/configuration/settings.html
- https://docs.mautic.org/en/6.0/contacts/custom_fields.html

> **Defects to flag:** the CLI reference spells the field-analysis command **`mautic:fields:analse`** (missing "y") while the custom-fields page spells it `mautic:fields:analyse` — do not examine the spelling. The cron page's prose says `-integration` (single dash) while every code example uses `--integration=` — use the double dash. Neither the CLI page nor the cron page is a complete command list.
> **NO OFFICIAL MAUTIC REFERENCE** for per-command recommended frequencies beyond the 15-minute stagger example and the weekly MaxMind pair.

---

### Module 11 — Updating Mautic, Backup & Restore

**Learning objectives**

1. Define what Mautic considers an acceptable backup.
2. Update a non-Composer install from the command line.
3. Update a Composer-managed install through the full documented sequence.
4. Roll back a failed Composer update.
5. Set an appropriate update stability level.
6. Diagnose and recover from a failed update.
7. Build a staging environment to rehearse an update.

**Key content**

*The backup rule.* The documentation states, twice, that you must have a **tested backup** — files *and* database, downloaded, **re-created in a separate test environment, and verified working**. "This is your only recourse if there are any problems with the update. Never update without having a working, up-to-date backup." A dump that has never been restored does not meet Mautic's own definition of a backup.

*Non-Composer CLI update:*

```
cd /your/mautic/directory
php bin/console mautic:update:find
php bin/console mautic:update:apply
php bin/console mautic:update:apply --finish
```

`mautic:update:find` links to the release announcement post, which states what the release contains and flags unmet environment requirements.

*Composer update, in order:* back up **`composer.lock` and `composer.json`** → bump every `mautic/` package (and anything added manually or via the Marketplace) in `composer.json`, or replace the whole file with the matching version from `mautic/recommended-project` → `composer update --with-dependencies` → `git diff` to find changed scaffolding files and restore customisations (**commonly `.htaccess`**) → **commit everything in a single commit** so `docroot` stays in sync with core for branch checkouts and `git bisect` → then the database block:

```
bin/console cache:clear
bin/console mautic:update:apply --finish
bin/console doctrine:migration:migrate --no-interaction
bin/console cache:clear
```

**Rollback:** restore `composer.json` and `composer.lock`, then run `composer install`.

*Browser updates.* Deprecated in **Mautic 4.2** and **completely removed from Mautic 5.0** — updates must be run at the command line. Browser updates chiefly failed through resource limitation, particularly on shared hosting.

*Stability levels.* By default Mautic notifies about **stable releases only**; Alpha, Beta and Release Candidate can be enabled in configuration. **"Never enable early access releases for production instances."**

*Failed-update recovery, in order:* clear the cache (`php bin/console cache:clear` or `rm -rf var/cache`) → trigger the update manually (`mautic:update:find`, `mautic:update:apply`) → check migrations (`doctrine:migration:status`, then `doctrine:migration:migrate`) → update files manually (back up, delete, download the package, upload, unzip, restore **`config/local.php`** — `app/config/local.php` before Mautic 5.0 — then restore `media/files`, `plugins`, `themes`, `translations`). The schema-check URL is **`example.com/s/update/schema`**. Common PHP failures: `Allowed memory size exhausted` (raise `memory_limit`) and a missing **`ZipArchive`** extension.

*Staging rehearsal (official Knowledgebase procedure).* Disable cron jobs before snapshotting → deploy a server snapshot → create a DNS A record for the staging subdomain with a low TTL (**300 seconds** recommended) → update the vhost `ServerName` and SSL certificate paths and reload the web server → edit `local.php` and change **`site_url`** to the staging subdomain → `cache:clear` → run the update sequence (`mautic:update:find`, `mautic:update:apply`, `doctrine:migration:status`, `doctrine:migration:migrate`, `doctrine:schema:update --dump-sql`, `doctrine:schema:update`, `cache:clear`) → verify the version on the dashboard and check the error log via System Info.

*Backup mechanisms Mautic actually documents:* the installer's **"Backup existing tables?"** option and backup prefix (`--db_backup_tables` default `true`, `--db_backup_prefix` default `bak_`), which renames pre-existing tables rather than dropping them; the `composer.json`/`composer.lock` rollback pair; and the list of directories to preserve when replacing the codebase — `config/local.php`, `media/files`, `media/images`, `app/media/dashboards`, `plugins`, `themes`, `translations`.

**References**

- https://docs.mautic.org/en/6.0/getting_started/how_to_update_mautic.html
- https://docs.mautic.org/en/6.0/troubleshooting/troubleshooting.html
- https://docs.mautic.org/en/6.0/getting_started/how_to_install_mautic.html
- https://docs.mautic.org/en/6.0/getting_started/switching_composer.html
- https://docs.mautic.org/en/6.0/configuration/cron_jobs.html
- https://kb.mautic.org/article/how-to-set-up-a-staging-server-to-test-new-mautic-releases.html

> **Largest gap in this track.** Mautic's documentation makes a tested backup a hard precondition for every update but publishes **no backup or restore procedure** — no `mysqldump` invocation, no file-archive command, no restore step order, and **no `mautic:backup` console command exists**. Trainers must supply a standard MySQL + filesystem backup runbook and label it as agency practice, not Mautic documentation. Forum threads are on an official domain but are community posts, not authoritative documentation.
> **Internal contradiction:** the 6.0 update page carries a stale warning that browser-update removal is "planned in Mautic 5.0" alongside the correct statement that it has already been removed.

---

### Module 12 — Deployment & Preparing Mautic for Production

**Learning objectives**

1. Design a repeatable deployment for a Composer-managed Mautic instance.
2. Apply the correct post-deploy command sequence.
3. Configure environments and secrets for production.
4. Apply the documented production-readiness settings.
5. Recognise which production concerns Mautic does not document and plan for them explicitly.

**Key content**

- **Hosting posture.** Mautic "requires a robust hosting environment and should not be installed on shared hosting platforms" — shared hosting impairs performance, causes update failures and limits functionality. Recommended: **VPS or dedicated server**.
- **Web root contract.** For Composer/Recommended-Project installs the document root must be `<project>/docroot` (or `public` if renamed). This is the single explicit web-server instruction Mautic publishes.
- **Post-deploy sequence** (from the Composer update procedure, which doubles as the deploy runbook):

```
bin/console cache:clear
bin/console mautic:update:apply --finish
bin/console doctrine:migration:migrate --no-interaction
bin/console cache:clear
```

  Plus `bin/console mautic:assets:generate` to combine and minify bundle CSS/JS into production files, and re-application of file ownership and permissions.
- **Environments and secrets.** `.env` precedence `.env` → `.env.local` → `.env.$APP_ENV` → `.env.$APP_ENV.local`, with real environment variables winning. Production defaults `APP_ENV=prod`, `APP_DEBUG=0`. Compile with `composer dump-env prod`. Secrets must never be committed.
- **Scale mechanisms Mautic documents:** enable Symfony Messenger queueing (Doctrine, Redis, AMQP, Beanstalkd or Amazon SQS) and run `messenger:consume` under Supervisor or systemd; use webhook **Queue Mode**; enable campaign **summary statistics**; run contact imports in the background; parallelise `mautic:broadcasts:send` with non-overlapping `--min-contact-id`/`--max-contact-id` ranges; keep segments lean (`mautic:segments:stat` "detects Segments that can be deleted to save resources on rebuilds").
- **Housekeeping commands for production:** `mautic:maintenance:cleanup`, `mautic:unusedip:delete` ("deletes IP addresses that aren't used in any other database table"), `mautic:fields:analyse -t`.
- **Logs.** Application logs in `var/logs`, `max_log_files` default `7`, log file name pattern `mautic_%kernel.environment%.php`. Cron output should be redirected to a file per job.

**References**

- https://docs.mautic.org/en/6.0/getting_started/how_to_update_mautic.html
- https://docs.mautic.org/en/6.0/getting_started/switching_composer.html
- https://docs.mautic.org/en/6.0/configuration/settings.html
- https://docs.mautic.org/en/6.0/configuration/command_line_interface.html
- https://docs.mautic.org/en/6.0/troubleshooting/file_ownership_permissions.html
- https://devdocs.mautic.org/en/6.0/development-environment/environments.html
- https://mautic.org/mautic-requirements/

> **NO OFFICIAL MAUTIC REFERENCE** for: a deployment guide (there is no Deployment, Production or Performance page in the 6.0 docs — those paths 404), **maintenance mode** (Mautic has no documented maintenance mode; `mautic:maintenance:cleanup` is a data purge, not a mode), log rotation, health-check endpoints, metrics or APM. Teach these as engineering practice the integrator must design, and say plainly that Mautic does not prescribe them.

---

### Module 13 — Secure Setup & Maintenance

**Learning objectives**

1. Apply correct file ownership and permissions as a security control.
2. Harden the documented configuration surface — CORS, trusted hosts and proxies, cookies, HSTS, API exposure, upload restrictions.
3. Configure SAML SSO correctly, including the default role for provisioned users.
4. Follow Mautic's vulnerability disclosure policy.
5. Determine whether a given instance is still receiving security advisories.
6. Apply GDPR and CCPA data-lifecycle controls.

**Key content**

*Security-relevant defaults shipped in Mautic 6:* `cookie_secure => true`, `cookie_httponly => false`, `headers_sts => false` (**HSTS is off by default**), `headers_sts_expire_time => 60`, `cors_restrict_domains => true`, `cors_valid_domains => []`, `api_enabled => false`, `api_enable_basic_auth => false`, form upload `blacklisted_extensions => ['php','sh']`, `trusted_hosts => []` (responds to all hosts when empty). Cookie security is derived from whether `site_url` begins with `https`. Assets should be stored **outside the public web root**.

*File permissions* — see Module 3. The docs frame this explicitly as a security control: "If your files don't have the appropriate permissions in place, it's easier for hackers to intrude on your files."

*Authentication.* Mautic uses **basic authentication for users**, with **SAML SSO** available. Configure at **Configuration → User/Authentication Settings** by uploading the IDP metadata XML. **Entity ID** is the site URL; **Service Provider Metadata** is `https://example.com/saml/metadata.xml`; **Assertion Consumer Service** is `https://example.com/s/saml/login_check`. It is **recommended to create a non-Admin role as the default role for created users** — and if the default role is left empty, SSO will not create Mautic users at all. With SAML enabled all logins redirect to the IDP, but **`/s/login` remains available for direct logins** if accessed directly.

*Vulnerability disclosure.* Report **privately via GitHub** at `https://github.com/mautic/mautic/security`. "**Do not** post it in GitHub as an issue or a Pull Request, on the forums, or discuss it in Slack." Scope is **Mautic core, officially supported plugins, and the `*.mautic.org` network**; third-party plugins and individual instances are out of scope. Disclosure is **coordinated** — issues stay private until a fix exists. Out-of-sequence releases carry **at least two weeks' notice**. Starting with Mautic 3.0, **one minor version at a time receives security advisories — the most recent minor release**; there are no advisories for alphas, betas or release candidates. Mautic is a **CVE Numbering Authority under MITRE**.

*Data lifecycle.* `mautic:maintenance:cleanup --gdpr` deletes contacts inactive for **3 years** (`gdpr_user_purge_threshold` default **1095** days). CCPA: `mautic:donotsell:download` followed by `mautic:max-mind:purge`, recommended **once per week**. Tracking has an **Anonymize IP** option for GDPR, and `do_not_track_ips` / `do_not_track_bots` lists exist with a seeded bot list.

*Install-time hardening.* Use HTTPS. Mautic **5.1+ requires a complex admin password**. Turn **off** "Backup existing tables?" for a new install. Restrict CORS domains to your own sites.

**References**

- https://docs.mautic.org/en/6.0/troubleshooting/file_ownership_permissions.html
- https://docs.mautic.org/en/6.0/authentication/authentication.html
- https://docs.mautic.org/en/6.0/configuration/settings.html
- https://docs.mautic.org/en/6.0/configuration/cron_jobs.html
- https://github.com/mautic/mautic/blob/6.x/SECURITY.md
- https://mautic.org/security
- https://mautic.org/releases/

> **Significant gap.** There is **no security-hardening page in the Mautic 6.0 user documentation** — no "Secure setup", no hardening checklist, no guidance on restricting the installer or the `/s/` admin path. There is also **no documentation for two-factor authentication** anywhere in the Mautic 6 user or developer docs, and no 2FA tab in Configuration. The Security Team's own stated goals include providing documentation on securing an instance; that documentation does not currently exist. Trainers must supply a hardening checklist and label it as agency practice.

---

### Module 14 — Themes, Email Templating, MJML, CSS & JavaScript

**Learning objectives**

1. Build, package and install a Mautic theme that passes validation.
2. Read and write `config.json`, declaring builders and features correctly.
3. Author an MJML email theme and know which MJML components Mautic processes.
4. Use Mautic's token syntax accurately, including fallbacks and date formatting.
5. Style and embed forms, and choose the correct embed method for progressive profiling.
6. Use the tracking script and the documented JavaScript callbacks.

**Key content**

*Theme package structure* (from the official Creating Themes page):

```
name.zip
├── assets/
├── html/
│   ├── email.html.twig
│   ├── email.mjml.twig
│   ├── base.html.twig
│   └── message.html.twig
├── config.json
└── thumbnail.png
```

Landing-page and form themes additionally use `page.html.twig` and `form.html.twig`, with per-feature thumbnails.

*`config.json`:*

```json
{
  "name": "Great Theme",
  "author": "Mr. Robot",
  "authorUrl": "https://mautic.org",
  "builder": ["legacy", "grapesjsbuilder"],
  "features": ["email", "page", "form"]
}
```

`builder` accepts a string or an array; valid values are **`legacy`** and **`grapesjsbuilder`**. `features` accepts **`email`**, **`page`**, **`form`**. The GrapesJS builder reads this file to decide which themes it will list. Real examples in core: `themes/blank` declares both builders and all three features; `themes/brienz` declares `grapesjsbuilder` only, `email` only.

*Packaging and installing.* Thumbnail dimensions **400px wide × 600px high**. **Zip the contents of the folder, not the folder itself** — `config.json` must be in the root of the zip or the theme will not install. Install at **Settings → Themes → Choose file → Install**. The listing shows **Title, Author, Feature**. Pre-installed themes can be hidden but not deleted; re-uploading an existing theme overwrites its files. The default landing-page theme is set at **Settings → Configuration → Theme Settings**; the default email theme is the `theme_email_default` parameter (default `blank`). Warning: changing a theme after building a landing page can break content if the two themes do not use the same placeholders.

*MJML.* Mautic officially supports MJML, delivered by the **GrapesJsBuilderBundle** ("GrapesJS Builder with MJML support for Mautic"). There is **no `mjml/` folder** — MJML lives at **`html/email.mjml.twig`** alongside a compiled **`html/email.html.twig`**, and **both files must be present**. "In order to harness the power of MJML, you must code the whole Theme in MJML." Mautic processes most `<mj-head>` components — tested: `mj-breakpoint`, `mj-font`, `mj-html-attributes`, `mj-style`, `mj-title`, `mj-preview` — and states `<mj-attributes>` does not run. Tested `<mj-body>` components: `mj-button`, `mj-column`, `mj-divider`, `mj-image`, `mj-navbar`, `mj-section`, `mj-spacer`, `mj-text`. Bundled MJML themes named in the docs: **Brienz, Paprika, Confirm Me**, "available with the new builder only". Asset references use `getAssetUrl(...)`.

*Builders.* **GrapesJS** has been available since Mautic 3.3 and default since 4.0 (drag-and-drop blocks, Style Manager, Layer Manager, code access, Asset Manager). The **Legacy Builder** remains selectable. Enable/disable at **Settings → Plugins → GrapesJS**, then clear the cache at `var/cache`. **Code Mode** is a third option under the Advanced tab, allowing raw HTML — with **no preview**. GrapesJS plugin contexts are `page`, `email-mjml`, `email-html`.

*Legacy builder slot markup:* `data-slot="{type}"`, `data-slot-container="1"`, `data-section="1"` (fixed-width content), `data-section-wrapper="1"` (full-width container, enables background changes). Documented slot types: **`text`, `image`, `button`, `separator`**, plus **`dwc`** for dynamic web content.

*Tokens:*

| Token | Meaning |
|---|---|
| `{contactfield=FIELD}` | Contact field value |
| `{contactfield=FIELD\|default}` | Fallback if empty |
| `{contactfield=FIELD\|true}` | URL-encode the value |
| `{contactfield=DATEFIELD\|date}` / `\|time` / `\|datetime` | Date formatting |
| `{signature}` | User signature |
| `{tracking_pixel}` | Explicit tracking-pixel placement |
| `{unsubscribe_text}` / `{unsubscribe_url}` | Unsubscribe sentence / URL |
| `{resubscribe_url}`, `{dnc_url}` | Resubscribe / do-not-contact |
| `{webview_url}` / `{webview_text}` | Browser version |
| `{formfield=ALIAS}`, `{form=ID}`, `{pagelink=ID}`, `{assetlink=ID}`, `{focus=ID}` | Component references |

The tracking pixel is placed just before `</body>` unless repositioned with `{tracking_pixel}`. Custom builder fonts are added through the `editor_fonts` array in `local.php`. Email drafts require `'email_draft_enabled' => 1`.

*Forms — CSS and embedding.* Three embed methods: **JavaScript embed** (recommended; auto-updates when the form changes; supports auto-fill), **iFrame**, and **manual/self-hosted copy** (which does **not** reflect later changes made in Mautic; the JavaScript block is included once per page even with multiple forms). **Progressive profiling only works with the embedded options** — and Mautic imposes a limit of **200 submissions** from which it searches for existing form values. Styling controls: the **Use Theme style** toggle, the **Theme** dropdown (not all themes include form styling — check the Features column), and per-field **Label attributes**, **Input attributes**, **Field container attributes** and **Radio/Check box label attributes**, written as `style="color: red"`. Setting **Render Style to No** makes Mautic ignore those fields. Theme-level form overrides live at `html/MauticFormBundle/Builder/_style.html.twig` and `html/form.html.twig`. CMS shortcodes: Mautic landing pages `{form=ID}`, WordPress `[mautic type="form" id=ID]`, Joomla! `{mauticform ID}`, Drupal 7 `{mauticform id=ID width=300px height=300px}`.

*JavaScript.* The tracking script defines the global **`MauticTrackingObject`**, aliased **`mt`**, loading **`mtc.js`**, and fires `mt('send', 'pageview');`. Form callbacks are registered on **`MauticFormCallback`**, keyed by the form's API name, with generated field IDs of the form `mauticform_input_{formApiName}_{fieldAlias}`. Documented callbacks include `onValidate()`, `onValidateStart()`, `onValidateEnd(formValid)`, `onErrorMark()`, `onErrorClear()`, `onResponse()`, `onSubmitButtonDisable()`, `onSubmitButtonEnable()`, `onShowNextPage()`, `onShowPreviousPage()`. MauticJS helpers include `MauticJS.makeCORSRequest()`, `MauticJS.documentReady()`, `MauticJS.insertScript()`, and the custom DOM event `mauticPageEventDelivered`.

**References**

- https://docs.mautic.org/en/6.0/builders/creating_themes.html
- https://docs.mautic.org/en/6.0/builders/email_landing_page.html
- https://docs.mautic.org/en/6.0/themes/manage_themes.html
- https://docs.mautic.org/en/6.0/themes/code_mode.html
- https://docs.mautic.org/en/6.0/channels/emails.html
- https://docs.mautic.org/en/6.0/components/forms.html
- https://docs.mautic.org/en/6.0/components/dynamic_web_content.html
- https://docs.mautic.org/en/6.0/configuration/tracking_script.html
- https://devdocs.mautic.org/en/5.x/themes/legacy.html
- https://devdocs.mautic.org/en/5.x/themes/grapesjs.html
- https://devdocs.mautic.org/en/5.x/themes/forms.html
- https://devdocs.mautic.org/en/5.x/mauticjs_api/tracking_script.html
- https://devdocs.mautic.org/en/5.x/form_hooks/getting_started.html

> **Stub pages — do not teach from them:** `themes/theme_structure.html` and `themes/customizing_themes.html` are stubs whose entire content is a pointer to the developer docs; `components/landing_pages.html` is a four-line stub with **zero body text**. There is **no theme documentation at any 6.x path on devdocs** — theme internals exist only at `/en/5.x/`.
> **NO OFFICIAL MAUTIC REFERENCE** for: CSS as a discipline, JavaScript as a discipline, landing-page custom CSS/JS, an exhaustive `data-slot` type list (an acknowledged open gap in Mautic's own docs repository), or Mustache templating (Mautic themes are **Twig**).
> **MJML itself** is documented by its vendor at mjml.io — external, first-party, and must be labelled as such.

---

### Module 15 — Email Infrastructure, Service Providers & Deliverability

**Learning objectives**

1. Configure an email transport using a Symfony Mailer DSN.
2. Install and configure an API-based transport and understand its trade-offs.
3. Choose between immediate and queued delivery and configure the queue.
4. Configure bounce and unsubscribe handling.
5. Apply SPF, DKIM, DMARC and one-click unsubscribe requirements.
6. Diagnose email that is queued, pending or not sending.

**Key content**

*Transports.* Since Mautic 5 all email goes through **Symfony Mailer**, configured as a **DSN**. DSN parts: scheme, user, password, host, path, port, options — e.g. `smtp://user:pass@smtp.example.com:587?timeout=10`. Documented ports: **465 for SSL, 587 for TLS**, with the explicit advice to **avoid port 25 for security reasons**. The configuration form URL-encodes DSN values for you; **if you paste a DSN directly into `config/local.php` you must URL-encode it yourself**. The parameter is **`mailer_dsn`** (default `smtp://localhost:25`); the environment override is **`MAUTIC_MAILER_DSN`**. SMTP is the default transport.

*Adding an API transport.* Mautic ships only `symfony/mailer` — **every non-SMTP transport is a `composer require` the integrator must add**. The documented worked example is SendGrid:

```
composer require symfony/sendgrid-mailer
# DSN: sendgrid+api://KEY@default
```

Two critical, documented trade-offs for generic Symfony transports: they **do not support batch sending, even via API** ("They only send one Email per request, as opposed to a thousand Emails per request as is the case with some Mautic transports"), and they **do not support transport callback handling used for bounce management**.

*Mail send settings.* Name to send mail as, from address, **Reply to address**, **Custom return path (bounce) address** (note Gmail does not support a custom return path), **Email address length limit** (default **320**), **Mailer is owner**, and the service to send through.

*Immediate vs queued.* Immediate is the default and sends synchronously, which can slow Mautic when using a remote service and can hit resource or provider limits on large batches. Queued delivery is recommended for high volume: Mautic stores the message until `messenger:consume email` runs. Queueing is **off by default** (`sync://`). See Module 9 for transports and retry settings.

*Bounce and unsubscribe handling.* Two mechanisms exist: **IMAP monitoring** and **provider webhooks**. Monitored inbox folders: **Default Mailbox, Bounces, Unsubscribe Requests, Contact Replies**, polled by `mautic:email:fetch`, each defaulting to port **993** with SSL. Mautic uses **plus-addressing** on the return path or List-Unsubscribe header — `youraddress+bounce_abc123@example.com` — so **the mailbox provider must support sub-addressing**. Selecting an Unsubscribe folder also makes Mautic append the email to the **List-Unsubscribe** header. Providers documented as supporting webhook callbacks for bounce management: **Elastic Email, SparkPost, Mandrill, Mailjet, SendGrid and Amazon SES**. Combine with the transport caveat above: **with a stock Symfony transport, IMAP monitoring is the only bounce path.**

*Message settings and unsubscribe.* `{webview_text}` default is "Having trouble reading this Email? Click here."; the tracking pixel goes just before `</body>`; the preference centre exposes segments, frequency, pause dates, categories and preferred channel through configuration toggles; `|EMAIL|` and `|URL|` in the confirmation messages must not be edited.

*Deliverability.* Mautic's official guidance on SPF/DKIM/DMARC exists as a **blog post, not documentation**: add an SPF TXT record (`v=spf1 a mx include:yourserver.com ~all`), publish a DKIM public key TXT record and enable signing on the mail server, and start DMARC at `p=none` (`v=DMARC1; p=none; rua=mailto:...`) before escalating to `quarantine` then `reject`. Bulk senders must provide **one-click unsubscribe compliant with RFC 8058 and RFC 2369** — shipped in **Mautic 5.0** and back-ported to **4.4.11**, so present in Mautic 6. Monitoring tools named: **Google Postmaster Tools, Microsoft SNDS, Sender Score, Barracuda Central**.

*Diagnosis.* The Knowledgebase's send-failure checklist: a test email has the subject "Mautic test email"; **pending vs sent** counters; **queued** usually means a frequency-rule cap; **one email (same email ID) can only be sent once to the same contact**; segments include contacts without email addresses. Bot filtering parameters exist (`bot_helper_bot_ratio_threshold` 0.6, `bot_helper_time_email_threshold` 2 seconds).

**References**

- https://docs.mautic.org/en/6.0/configuration/settings.html
- https://docs.mautic.org/en/6.0/channels/emails.html
- https://docs.mautic.org/en/6.0/configuration/cron_jobs.html
- https://docs.mautic.org/en/6.0/configuration/command_line_interface.html
- https://mautic.org/blog/navigating-gmail-and-yahoos-new-spam-policies-what-mautic-users-need-know/
- https://kb.mautic.org/article/email-sending-doesn-039%3Bt-work-here-are-10-things-to-check.html
- https://github.com/mautic/mautic/blob/6.x/app/bundles/EmailBundle/Config/config.php

> **NO OFFICIAL MAUTIC REFERENCE** for: per-provider setup pages for Amazon SES, Mailgun, Postmark, Brevo/Sendinblue, Elastic Email, Gmail, Sendmail, Mailjet or Mandrill in the 6.0 docs; a dedicated deliverability page (there is none); or Google Postmaster Tools beyond a single blog mention. **Trap to correct explicitly:** `plugins/amazon.html` is the **Amazon S3 asset-storage plugin, not SES**.
> **Stale content:** the Knowledgebase send-failure article still references the filesystem spool at `/var/spool` and the command `mautic:emails:send`, **which does not exist in Mautic 6** — the EmailBundle on `6.x` contains only `ProcessFetchEmailCommand` and `SendWinnerEmailCommand`. Teach `messenger:consume email`.

---

### Module 16 — Integrations: Plugins, Webhooks & the REST API

**Learning objectives**

1. Enable and manage plugins, and test an integration three different ways.
2. Configure the major documented CRM and service integrations.
3. Design and secure a webhook consumer, including signature verification.
4. Enable the REST API and authenticate with Basic Auth or OAuth2.
5. Use the core REST endpoints for contacts, segments, campaigns, emails and forms.
6. Choose the right integration mechanism for a given requirement.

**Key content**

*Plugins.* "Mautic Plugins are installable packages which can extend Mautic feature or integrate it with another system." Found under the **Admin (cog) menu**. On a new install, click **Install/Upgrade Plugins** to enable the defaults; if a plugin still does not appear, clear the cache from the CLI and retry. CLI: `mautic:plugins:reload` (aliases `mautic:plugins:install`, `mautic:plugins:update`). Developer view: plugins are **Symfony bundles** installed into `plugins/`, namespaced `MauticPlugin\[Plugin Folder Name]\`, with `Config/config.php` registering routes, menu items, services and parameters, and a bundle class extending `AbstractPluginBundle`. Lifecycle events `PluginEvents::ON_PLUGIN_INSTALL` and `ON_PLUGIN_UPDATE` were added in **Mautic 4.2.0**; **there is no uninstall hook**.

*Three documented ways to test an integration:* a campaign **Push Contact to Integration** action; a standalone **form** with the push action; or a **points trigger** at a threshold. Contact field mapping only needs to cover the fields you intend to sync.

*Integrations with real documentation in Mautic 6:* **Amazon S3** (asset storage — Access Key ID, Secret Access Key, bucket name and region), **Clearbit** (API key; instance must be publicly reachable), **HubSpot** (private-app API key with Contacts and Companies scopes; pull with `mautic:integration:fetchleads --integration=Hubspot --fetch-all`; HubSpot's endpoints pull only contacts modified in the last 30 days), **MailChimp** (account username + API key; the Contact Field Mapping tab appears only after selecting a list, saving and reopening), **Social login** (Twitter/X, Facebook, LinkedIn — callback URL, key, secret), **Twilio** (Account SID, Auth Token, plus a Messaging Service ID on the Features tab; callback `https://example.com/sms/twilio/callback`), **Vtiger** (URL, username, Access Key from My Preferences), **WordPress/WPMautic** (base URL, script location, track logged-in users, fallback pixel activation), **Zoho CRM** (OAuth 2.0 Server Based Application; must select the correct data centre; pulls Leads, Contacts and/or Accounts; empty required values are sent as "Unknown"; **all accounts must be configured in English for sync to work**). **Salesforce** is documented only in the Knowledgebase: a Connected App with the *Access and manage your data (API)* and *Perform requests on your behalf at any time* scopes, Consumer Key/Secret into Mautic, API sync every **8–10 minutes**, and an optional custom **Timeline** object with seven fields carrying the **last 7 days** of activity.

*Webhooks.* Configure at **Configuration → Webhook Settings**. **Queue Mode** is either **Process Events Immediately** (real-time, single event) or **Queue Events Only — Process Via CLI Command** (batched, delivered by `mautic:webhooks:process`); event order is chronological or reverse chronological. Create a webhook under **Webhooks → New** with a Name, POST URL, selected triggering events and an auto-generated, editable secret. **Payload structure is keyed by event type**: `{ "EventType": [ {payload}, {payload} ] }`, and queued delivery groups multiple event types into one request. **Signature verification:** the **`Webhook-Signature`** header carries a **base64-encoded HMAC-SHA256 of the raw request body** using the webhook secret; recompute over the raw body and compare. A **Send Test Payload** button exists. Documented events include `mautic.lead_post_save_new`, `lead_post_save_update`, `lead_points_change`, `lead_post_delete`, `lead_channel_subscription_changed`, `lead_company_change`, `company_post_save`, `company_post_delete`, `email_on_send`, `email_on_open`, `form_on_submit`, `page_on_hit`, `sms_on_send`. The full runtime list is retrievable from **`GET /hooks/triggers`**. Config keys: `webhook_limit` 10, `webhook_time_limit` 600 s, `webhook_log_max` 1000, `webhook_disable_limit` 100, `webhook_timeout` 15 s.

*REST API.* **Disabled by default** — enable at **Configuration → API Settings** or `'api_enabled' => 1`. Base endpoint `https://mautic.example.com/api`; all responses are JSON; every response carries a **`Mautic-Version`** header (since 2.4.0).

**Authentication.** Two methods: **Basic Auth** (must be separately enabled; `Authorization: Basic base64(user:password)`) and **OAuth2**, which Mautic recommends. OAuth2 credentials are created under **API Credentials** in the admin menu. Authorization Code flow: `GET /oauth/v2/authorize?grant_type=authorization_code&client_id=…&redirect_uri=…&response_type=code&state=…`, then `POST /oauth/v2/token`. Client Credentials flow returns an access token with **no refresh token**. Requests carry `Authorization: Bearer ACCESS_TOKEN`. Defaults: access token **60 minutes**, refresh token **14 days**. Rate limiting is configured via `api_rate_limiter_limit` (0 = unlimited) and `api_rate_limiter_cache`; `api_batch_max_limit` is **200**.

**Core endpoints.** Contacts: `GET /contacts/ID`, `GET /contacts`, `POST /contacts/new`, `POST /contacts/batch/new`, `PATCH|PUT /contacts/ID/edit`, `DELETE /contacts/ID/delete`, plus DNC (`/contacts/ID/dnc/CHANNEL/add|remove`), points (`/contacts/ID/points/plus|minus/POINTS`), point groups, `/contacts/ID/segments`, `/contacts/ID/campaigns`, `/contacts/ID/activity`, `/contacts/list/fields`. **PATCH returns 404 if the record does not exist; PUT creates it.** List parameters: `search`, `start` (default 0), `limit` (**default 30**), `orderBy`, `orderByDir`, `publishedOnly`, `minimal`. Segments, campaigns (including `GET /campaigns/export/ID` and `POST /campaigns/import`), emails (including `POST /emails/ID/contact/CONTACT_ID/send`), forms, fields, companies, webhooks and `GET /stats` follow the same shape. The official client is **`composer require mautic/api-library`** (PHP 8.2+, requires a separate PSR-18 HTTP client such as Guzzle).

*Choosing a mechanism.* Plugin (bundled or Marketplace) → webhook (Mautic pushes on an event) → REST API (an external system pulls or pushes on its own schedule) → an automation platform sitting on top of the API and webhooks.

**References**

- https://docs.mautic.org/en/6.0/plugins/plugin_resources.html
- https://docs.mautic.org/en/6.0/plugins/hubspot.html
- https://docs.mautic.org/en/6.0/plugins/zoho_crm.html
- https://docs.mautic.org/en/6.0/plugins/mailchimp.html
- https://docs.mautic.org/en/6.0/plugins/twilio.html
- https://docs.mautic.org/en/6.0/plugins/amazon.html
- https://docs.mautic.org/en/6.0/plugins/social_login.html
- https://docs.mautic.org/en/6.0/plugins/vtiger.html
- https://docs.mautic.org/en/6.0/plugins/wordpress.html
- https://docs.mautic.org/en/6.0/plugins/clearbit.html
- https://kb.mautic.org/article/how-to-integrate-mautic-with-salesforce.html
- https://devdocs.mautic.org/en/6.0/rest_api/getting_started.html
- https://devdocs.mautic.org/en/6.0/rest_api/authentication.html
- https://devdocs.mautic.org/en/6.0/rest_api/contacts.html
- https://devdocs.mautic.org/en/6.0/rest_api/segments.html
- https://devdocs.mautic.org/en/6.0/rest_api/campaigns.html
- https://devdocs.mautic.org/en/6.0/rest_api/emails.html
- https://devdocs.mautic.org/en/6.0/rest_api/forms.html
- https://devdocs.mautic.org/en/6.0/rest_api/webhooks.html
- https://devdocs.mautic.org/en/6.0/webhooks/getting_started.html
- https://devdocs.mautic.org/en/6.0/webhooks/example_scripts.html
- https://devdocs.mautic.org/en/6.0/webhooks/events/index.html
- https://devdocs.mautic.org/en/6.0/plugin_integrations/integrations.html
- https://github.com/mautic/api-library

> **Empty stubs — 10 of the 21 plugin pages in the Mautic 6.0 docs have no body text at all:** ConnectWise, FullContact, iContact, **Microsoft Dynamics CRM**, Microsoft Outlook, **Pipedrive**, **SugarCRM**, Tag Manager, Twitter, **Zapier**. Every CRM except HubSpot and Zoho is undocumented (Salesforce only via the Knowledgebase). **No exam question may be sourced from these plugins.**
> **NO OFFICIAL MAUTIC REFERENCE** for **n8n** (only a 2022 community blog post on mautic.org — a blog post, not documentation), **Make/Integromat**, or **Postman** (a Postman collection is referenced only in an open documentation issue). Teach these as tooling concepts against the documented REST API and webhook contracts, and label the sources as external.

---

## 7. Verified documentation defects, stubs and gaps

Trainers must brief candidates on these before the exam, and no exam question may be sourced from a stub or stale page.

### Empty or near-empty stubs

| Page | Status |
|---|---|
| `docs.mautic.org/en/6.0/components/landing_pages.html` | 4 lines of source, **zero body text** |
| `docs.mautic.org/en/6.0/themes/theme_structure.html` | Stub — pointer to devdocs 5.x only |
| `docs.mautic.org/en/6.0/themes/customizing_themes.html` | Stub — pointer to devdocs 5.x only |
| `docs.mautic.org/en/6.0/plugins/` — connectwise, fullcontact, icontact, microsoft_dynamics_crm, microsoft_outlook, pipedrive, sugar_crm, tag_manager, twitter, zapier | **10 empty stubs** |
| `devdocs.mautic.org/en/6.0/plugin_extensions/webhooks.html` | Empty stub |
| `devdocs.mautic.org/en/6.0/plugin_miscellaneous/commands.html` | Empty stub |
| `devdocs.mautic.org/en/6.0/rest_api/focus.html`, `tweets.html`, `data.html` | Empty stubs |
| `docs.mautic.org/en/6.0/queue/message_queue.html` | Very thin |

### Stale or self-contradictory content

| Item | Problem |
|---|---|
| `queue/queue.html` | Documents pre-Messenger RabbitMQ/Beanstalkd and the non-existent `mautic:email:send` |
| `mautic/recommended-project:^5` in the 6.0 docs and the 6.x README | Stale version constraint; README also claims PHP 7.4 minimum |
| `how_to_update_mautic.html` | Says browser-update removal is "planned in 5.0" *and* that it was removed in 5.0 |
| `app/config/local.php` in `custom_fields.html` and `file_ownership_permissions.html` | Mautic 5+ uses `config/local.php` |
| "Default item limit per page… default is 10" in `settings.html` | Shipped default is `default_pagelimit => 30` |
| `mautic:fields:analse` in the CLI reference | Typo; the correct spelling is `mautic:fields:analyse` |
| `-integration` in the cron page prose | Should be `--integration=` |
| `https://mautic.ddev` in the contributor handbook | Should be `https://mautic.ddev.site` |
| PHP extension list in the contributor handbook | Conflicts with the requirements page (which is authoritative) |
| KB "email sending doesn't work" article | References `/var/spool` and `mautic:emails:send`, both gone in Mautic 6 |
| DDEV blog post | PHP 7.3, MailHog :8025, PHPMyAdmin :8036 — superseded by the repo config |
| Mautic 6 ELTS | `mautic.org/releases/` and the ELTS page disagree |
| `docs` say `getAssetUrl('Themes/'~Theme~…)`; shipped themes use `getAssetUrl('themes/'~template~…)` | Documentation and code disagree |
| Docs say `<mj-attributes>` does not run; core theme Brienz uses it | Documentation and code disagree |

### Topics with no official Mautic reference at all

These remain in the curriculum but must be taught from external first-party sources, clearly labelled:

- **Backup and restore procedure** (no `mysqldump`, no restore runbook, no `mautic:backup` command)
- **Deployment guide, production/performance page, maintenance mode, log rotation, monitoring/health checks/metrics**
- **Web server configuration** (no vhost, Nginx block, `.htaccess` contents, or PHP-FPM tuning)
- **Database privileges, charset/collation, index tuning, MySQL sizing, ER diagram / core table schema**
- **Two-factor authentication** and **security hardening guidance** of any kind
- **CSS basics**, **JavaScript basics** as disciplines, **landing-page custom CSS/JS**, **exhaustive `data-slot` list**
- **MJML as a language** (vendor: mjml.io)
- **Email deliverability** as a maintained reference (only a 2024 blog post)
- **Per-provider ESP setup** (SES, Mailgun, Postmark, Brevo, Elastic Email, Gmail, Sendmail, Mailjet, Mandrill)
- **n8n, Make/Integromat, Postman, Zapier**
- **Shell scripting**, **PHP as a language**, **Symfony as a framework** beyond Mautic's own usage
- **Custom Objects** in Mautic 6 core documentation

---

## 8. Preparation recommendations

1. **Build twice, break once.** Install Mautic once from the zip package and once from the Recommended Project, then convert a zip install to Composer. Most Integrator exam failures are Composer-layout failures.
2. **Run a DDEV instance for the whole study period.** `ddev start`, then use `ddev exec bin/console` for every command in Module 10 at least once and read its `--help`.
3. **Read the shipped configuration.** Open `app/bundles/CoreBundle/Config/config.php`, `EmailBundle`, `ApiBundle`, `MessengerBundle` and `WebhookBundle` on the `6.x` branch. Because there is no parameter reference page, the code *is* the reference.
4. **Wire one real integration end to end** — a webhook consumer that verifies the `Webhook-Signature` header, plus an OAuth2 REST client that creates and updates a contact.
5. **Rehearse an update on a staging clone** following the Knowledgebase procedure, including changing `site_url` and clearing the cache.
6. **Test a live pull request** through Gitpod or Codespaces so the contribution workflow is muscle memory rather than theory.
7. **Memorise the numbers.** PHP 8.1–8.3; MySQL 5.7 / MariaDB 10.2; `max_execution_time` ≥ 240; segment and campaign batch 300; campaign trigger batch 100; broadcast limit 100; access token 60 minutes; refresh token 14 days; API batch max 200; webhook timeout 15 s; GDPR purge 1095 days; ports 465/587; MJML thumbnail 400×600.
8. **Know what is *not* documented.** A significant share of real integrator work — backups, hardening, deployment, deliverability — has no official Mautic reference. Knowing that, and knowing where the boundary sits, is itself an examinable competency.

---

## 9. Validity and maintenance of this curriculum

- Reviewed against **Mautic 6.0** documentation as of **31 August 2026**.
- Re-verify every reference when the certification baseline moves to a new major release, and re-check the stub list in §7 — several of these pages are open documentation issues and may be filled in.
- Certification is valid for **24 months** from award.
