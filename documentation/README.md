# Tradewell documentation

Tradewell 2.0.1 by **Prosper Technologies** is a WordPress block theme for HVAC, plumbing, roofing, electrical and solar businesses. It uses WordPress Full Site Editing. Elementor and WooCommerce integrations are not included.

## Install

1. Unzip the main download on your computer.
2. In WordPress, open **Appearance → Themes → Add New → Upload Theme**. Select `tradewell.zip`, install and activate it.
3. Open **Appearance → Install Plugins** and install and activate Tradewell Leads. TGMPA downloads it from this public repository after you choose to install it.
4. If the download is blocked, use **Plugins → Add New → Upload Plugin** with `plugins/tradewell-leads.zip` from the main download.
5. Open **Leads → Setup wizard**, pick a trade, enter the business details and build the starter site.

The main download is not itself an installable theme. Requirements: WordPress 6.6+, PHP 7.4+. A current supported PHP version is recommended.

## Edit your website

- **Pages → Home → Edit:** edit, reorder or remove imported homepage sections.
- **Appearance → Editor:** edit header, footer, menus, colors and typography. There are five trade style variations plus the default palette.
- **Leads → Settings:** update business information, telephone, notification addresses, currency, consent wording, service areas and mobile call bar.
- **Leads → Service areas:** add public service-area pages and their ZIP codes.
- **Pages → Contact / Book Online:** edit booking services, offered dates and arrival windows in the block sidebar.
- **Optional child theme:** install and activate `tradewell-child.zip` alongside the parent before adding custom PHP or CSS. Both stylesheets load in the correct order.

Without a starter import, the theme honours **Settings → Reading** and displays WordPress's normal latest-posts view. The theme works without the plugin; lead tools require the plugin. Switching themes retains your leads.

## Demo content and rebuilds

All sample reviews, staff names, ratings, response times, prices, license numbers and statistics are placeholders. Replace them with truthful business information before publishing. Illustrations and icons are included; stock photography is not used.

**Back up before rebuilding or removing a starter site.** Those actions permanently remove imported pages, including your edits to them, and replace imported navigation and templates. Separately created pages and posts are kept.

## Quotes and bookings

The estimator uses `(base + size × unit price) × urgency`, with the configured range spread. Edit its services, units and prices in the block sidebar. Estimates are indicative and do not commit your business to a price. The technician must confirm scope and final pricing. Booking submissions are requests; confirm availability with the customer.

Forms use a signed token, honeypot and a default limit of six accepted submissions per client per ten minutes. Tokens expire after fourteen days: keep page-cache lifetimes shorter and refresh an expired form. These controls reduce spam but do not replace host-level abuse protection.

## Lead delivery and privacy

Successfully accepted requests are saved in the administrator-only leads inbox. Set the notification email under **Leads → Settings**. Use an authenticated SMTP integration if your host does not deliver mail reliably, and send a test before launch.

An optional webhook sends the submitted details to the endpoint you configure. Leave it empty to disable delivery. Use a trusted public HTTPS endpoint and disclose the recipient in your privacy policy. No telemetry is sent to Prosper Technologies.

WordPress **Tools → Export Personal Data / Erase Personal Data** includes matching leads by email. These operations paginate through all matching records. Configure an appropriate retention policy. Use the administrator-only CSV export for your own secure workflow; keep customer information out of public support issues.

The plugin suggests privacy-policy wording under **Settings → Privacy**. Review that text and the form consent wording for your business.

## Analytics and SEO

No tracking service is included. If you add a tag manager, arrange the necessary visitor consent before enabling it. Events are `tradewell_lead` (lead type, service, estimate), `tradewell_call` (link class), `tradewell_quote_step` (service) and `tradewell_area_check` (served status). ZIP codes and contact details are not included in the built-in analytics events.

The plugin can output LocalBusiness structured data using the business settings. If another SEO plugin supplies equivalent markup, disable ours with `add_filter( 'twleads_output_schema', '__return_false' );`. Use your preferred SEO plugin for meta descriptions and other SEO settings.

## Troubleshooting

- **Missing style.css during installation:** upload the inner `tradewell.zip`, not the complete download ZIP.
- **Plugin download blocked:** install the included plugin ZIP manually.
- **Service-area or page 404:** open **Settings → Permalinks → Save Changes**.
- **Too many requests during testing:** wait ten minutes or temporarily adjust `twleads_rate_limit` on an isolated test site.
- **Email not received:** check the leads inbox and your SMTP delivery logs.
- **Playground will not start:** try a current desktop browser. Playground uses browser-based PHP and storage; it is not equivalent to conventional WordPress hosting and cannot deliver real email.

## Translation and custom code

Translation catalogs: `tradewell/languages/tradewell.pot` and `tradewell-leads/languages/tradewell-leads.pot`. Text domains are `tradewell` and `tradewell-leads`. Theme-specific functions use `tradewell_`; plugin functions use `twleads_`. Existing `twl/` blocks and the `twl/v1` REST namespace remain stable.

Useful hooks: `twleads_lead_created`, `twleads_lead_errors`, `twleads_webhook_payload`, `twleads_rate_limit`, `twleads_show_callbar`, `twleads_schema` and `twleads_output_schema`.

## Licensing and support

Theme and plugin source, CSS, icons and illustrations: **GPL v2 or later**. Archivo: SIL Open Font License 1.1, The Archivo Project Authors. TGM Plugin Activation: GPL v2 or later, Thomas Griffin, Gary Jones and Juliette Reinders Folmer. License texts and credits are included in the main download.

The main download includes a fully illustrated HTML manual in `documentation/index.html`. [Report product issues](https://github.com/ProsperTechnology/tradewell-demo/issues) without sharing customer records or credentials. After marketplace publication, use the item's Support tab for purchase-specific support.
