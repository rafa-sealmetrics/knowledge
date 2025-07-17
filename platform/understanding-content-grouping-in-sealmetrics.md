---
title: Understanding Content Grouping in Sealmetrics
description: ''
slug: understanding-content-grouping-in-sealmetrics
---
[Skip to main content](#main-content)![Image](understanding-content-grouping-in-sealmetrics/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Platform](https://help.sealmetrics.com/en/collections/10013736-platform)Content Grouping is a powerful feature in Sealmetrics that allows you to organize your page views into logical groups, enabling you to analyze related pages as a single unit. This feature helps you understand the performance of content categories rather than individual pages.



What is Content Grouping?

Content Grouping lets you categorize multiple URLs under a single group name. Instead of analyzing each page individually, you can group related pages together and get aggregated data for the entire group.

Example scenarios:

Group all blog posts under "Blog Content"Categorize product pages as "Product Catalog"Organize help documentation under "Support Pages"Group checkout pages as "Purchase Flow"

Group all blog posts under "Blog Content"

Group all blog posts under "Blog Content"

Categorize product pages as "Product Catalog"

Categorize product pages as "Product Catalog"

Organize help documentation under "Support Pages"

Organize help documentation under "Support Pages"

Group checkout pages as "Purchase Flow"

Group checkout pages as "Purchase Flow"

How Content Grouping Works

When you implement content grouping, Sealmetrics will:

Collect page viewsfrom individual URLs as usualApply the group classificationyou've definedAggregate metricsfor all pages within each groupProvide unified reportingfor grouped content

Collect page viewsfrom individual URLs as usual

Collect page viewsfrom individual URLs as usual

Apply the group classificationyou've defined

Apply the group classificationyou've defined

Aggregate metricsfor all pages within each group

Aggregate metricsfor all pages within each group

Provide unified reportingfor grouped content

Provide unified reportingfor grouped content

Setting Up Content Grouping

Method 1: Global Tracker Configuration

The easiest way to add content grouping is through the Global Tracker in your Sealmetrics dashboard:

Access Global Tracker: Go to your Sealmetrics dashboard and navigate to the Global Tracker sectionSelect Page View: Choose "Page view" from the tracking optionsEnable Content Grouping: Toggle "Yes" for "Add content grouping to your page view"Configure Your Code: The tracker will automatically generate code with thecontent_groupingparameter

Access Global Tracker: Go to your Sealmetrics dashboard and navigate to the Global Tracker section

Access Global Tracker: Go to your Sealmetrics dashboard and navigate to the Global Tracker section

Select Page View: Choose "Page view" from the tracking options

Select Page View: Choose "Page view" from the tracking options

Enable Content Grouping: Toggle "Yes" for "Add content grouping to your page view"

Enable Content Grouping: Toggle "Yes" for "Add content grouping to your page view"

Configure Your Code: The tracker will automatically generate code with thecontent_groupingparameter

Configure Your Code: The tracker will automatically generate code with thecontent_groupingparameter

Generated Code Example:





![Image](understanding-content-grouping-in-sealmetrics/content-grouping.png)



Key Configuration Parameters

When implementing content grouping, you'll work with these key parameters in your tracking code:

account: Your unique Sealmetrics account IDevent: Set to'pageview'for page view trackingcontent_grouping: The group name for the current page (e.g.,'blog-content','product-catalog')use_session: Session tracking parameter (typically set to1)

account: Your unique Sealmetrics account ID

account: Your unique Sealmetrics account ID

event: Set to'pageview'for page view tracking

event: Set to'pageview'for page view tracking

content_grouping: The group name for the current page (e.g.,'blog-content','product-catalog')

content_grouping: The group name for the current page (e.g.,'blog-content','product-catalog')

use_session: Session tracking parameter (typically set to1)

use_session: Session tracking parameter (typically set to1)

Important Notes:

Content group names should use lowercase and hyphens (e.g.,'blog-content'instead of'Blog Content')Keep group names consistent across your siteThecontent_groupingparameter must be included in every page view you want to group.

Content group names should use lowercase and hyphens (e.g.,'blog-content'instead of'Blog Content')

Content group names should use lowercase and hyphens (e.g.,'blog-content'instead of'Blog Content')

Keep group names consistent across your site

Keep group names consistent across your site

Thecontent_groupingparameter must be included in every page view you want to group.

Thecontent_groupingparameter must be included in every page view you want to group.

Best Practices

Define Clear Categories: Create logical groups that align with your business objectives and content strategy.

Use Consistent Naming: Maintain consistent naming conventions across your content groups for easier analysis.

Avoid Over-Grouping: Don't create too many groups - focus on meaningful categorizations that provide actionable insights.

Regular Review: Periodically review and update your content groups as your site structure evolves.

Common Use Cases

E-commerce Sites

Group product categoriesSeparate informational vs. transactional pagesTrack funnel performance by content type

Group product categories

Group product categories

Separate informational vs. transactional pages

Separate informational vs. transactional pages

Track funnel performance by content type

Track funnel performance by content type

Content Publishers

Analyze performance by content topicsCompare different content formatsMeasure engagement across content categories

Analyze performance by content topics

Analyze performance by content topics

Compare different content formats

Compare different content formats

Measure engagement across content categories

Measure engagement across content categories

SaaS Platforms

Group feature pagesSeparate onboarding vs. support contentTrack user journey through content types

Group feature pages

Group feature pages

Separate onboarding vs. support content

Separate onboarding vs. support content

Track user journey through content types

Track user journey through content types

Troubleshooting

Q: How do I update the content grouping for existing pages?A: You need to update thecontent_groupingparameter in your tracking code and redeploy it to your pages. The Global Tracker in your dashboard can help generate the updated code.

Q: Can I use the same content group name across different sections?A: Yes, but ensure it makes sense for your analysis. Pages with the samecontent_groupingvalue will be aggregated together regardless of their URL structure.

Q: What happens if I don't set a content_grouping parameter?A: Pages without acontent_groupingparameter will not be included in content group reports, but will still appear in regular page-level analytics.

Q: How many content groups can I create?A: There's no strict limit, but we recommend keeping groups manageable (typically 10-20 groups) for optimal analysis.

[How SuperPrivacy Tracking Works](https://help.sealmetrics.com/en/articles/9667399-how-superprivacy-tracking-works)[How to track SPA sites:](https://help.sealmetrics.com/en/articles/9667469-how-to-track-spa-sites)[Setting Up Trackers in Sealmetrics](https://help.sealmetrics.com/en/articles/10054456-setting-up-trackers-in-sealmetrics)[SealMetrics Kick off [Video]](https://help.sealmetrics.com/en/articles/10364275-sealmetrics-kick-off-video)[How SealMetrics Calculates SEO Traffic](https://help.sealmetrics.com/en/articles/11154410-how-sealmetrics-calculates-seo-traffic)[SealMetrics Help Center](/en/)Company

Privacy PolicyDPATerms of UseData Privacy Audit

Privacy Policy

[Privacy Policy](https://legal.sealmetrics.com/privacy-notice)DPA

[DPA](https://legal.sealmetrics.com/DPA)Terms of Use

[Terms of Use](https://sealmetrics.com/terms-of-use/)Data Privacy Audit

[Data Privacy Audit](https://app.comply.org/attest/sealmetrics)Guides

Cookie Consent GuideSocial Media AuditCookieless & Google

Cookie Consent Guide

[Cookie Consent Guide](https://sealmetrics.com/mastering-the-cookie-consent-banner/)Social Media Audit

[Social Media Audit](https://sealmetrics.com/in-depth-analysis-of-social-media-privacy-policies/)Cookieless & Google

[Cookieless & Google](https://sealmetrics.com/how-google-is-navigating-the-cookieless-future/)Explore

Check out the live demoNewsletter

Check out the live demo

[Check out the live demo](https://app.sealmetrics.com/reports/cookieless/dashboard)Newsletter

[Newsletter](https://sealmetrics.com/privacy-marketing-newsletter/)