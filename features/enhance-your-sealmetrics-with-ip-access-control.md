---
title: Enhance Your Sealmetrics with IP Access Control
description: ''
slug: enhance-your-sealmetrics-with-ip-access-control
---
[Skip to main content](#main-content)![Image](enhance-your-sealmetrics-with-ip-access-control/a37799c64a3031dd8bee1ad2404decf7.png)

[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[Academy](https://sealmetrics.com/privacy-marketing-academy/)[Partners](https://sealmetrics.com/partners/)[All Collections](/en/)[Features](https://help.sealmetrics.com/en/collections/10013520-features)Welcome to an even more secure Sealmetrics experience! We're excited to introduce IP-based access control, giving you complete control over who can access your analytics dashboard.



🔐 Your Security Matters

Now you can add an extra layer of protection to your Sealmetrics dashboard by restricting access to specific IP addresses. This enterprise-grade security feature ensures that only authorized users from approved locations can view your valuable analytics data.



Setting Up IP Access Control



![Image](enhance-your-sealmetrics-with-ip-access-control/Seal-Metrics-02-13-2025_04_03_PM.png)





Follow these simple steps on your screen to configure IP access:

Navigate to the Security Settings in your dashboardAdd the approved IP addresses or rangesSave your configuration

Navigate to the Security Settings in your dashboard

Navigate to the Security Settings in your dashboard

Add the approved IP addresses or ranges

Add the approved IP addresses or ranges

Save your configuration

Save your configuration

Your team can continue accessing the dashboard seamlessly from the authorized IPs, while unauthorized access attempts will be automatically blocked.



CIDR (Classless Inter-Domain Routing) notation is a standardized method for representing IP address ranges. This guide will help you understand how CIDR works and its common applications in network configuration.



What is CIDR Notation?

CIDR notation consists of two parts:

An IP address (e.g., 192.168.1.0)A suffix number after a forward slash (e.g., /24)

An IP address (e.g., 192.168.1.0)

An IP address (e.g., 192.168.1.0)

A suffix number after a forward slash (e.g., /24)

A suffix number after a forward slash (e.g., /24)

The suffix indicates how many bits are used for the network portion of the address, which determines the size of the IP range.



Common CIDR Examples Explained

Small Private Network Range

192.168.1.0/24

Range: 192.168.1.0 - 192.168.1.255Total addresses: 256Perfect for: Home networks or small office setupsCommon usage: Local area networks (LANs)

Range: 192.168.1.0 - 192.168.1.255

Range: 192.168.1.0 - 192.168.1.255

Total addresses: 256

Total addresses: 256

Perfect for: Home networks or small office setups

Perfect for: Home networks or small office setups

Common usage: Local area networks (LANs)

Common usage: Local area networks (LANs)

Complete Private Network Range

192.168.0.0/16

Range: 192.168.0.0 - 192.168.255.255Total addresses: 65,536Perfect for: Medium-sized organizationsCommon usage: Larger office networks with multiple departments

Range: 192.168.0.0 - 192.168.255.255

Range: 192.168.0.0 - 192.168.255.255

Total addresses: 65,536

Total addresses: 65,536

Perfect for: Medium-sized organizations

Perfect for: Medium-sized organizations

Common usage: Larger office networks with multiple departments

Common usage: Larger office networks with multiple departments

Large Corporate Network Range

10.0.0.0/8

Range: 10.0.0.0 - 10.255.255.255Total addresses: 16,777,216Perfect for: Large enterprisesCommon usage: Corporate networks with multiple locations

Range: 10.0.0.0 - 10.255.255.255

Range: 10.0.0.0 - 10.255.255.255

Total addresses: 16,777,216

Total addresses: 16,777,216

Perfect for: Large enterprises

Perfect for: Large enterprises

Common usage: Corporate networks with multiple locations

Common usage: Corporate networks with multiple locations

Single Host Configuration

203.0.113.25/32

Range: Only 203.0.113.25Total addresses: 1Perfect for: Specific host targetingCommon usage: Firewall rules for individual servers

Range: Only 203.0.113.25

Range: Only 203.0.113.25

Total addresses: 1

Total addresses: 1

Perfect for: Specific host targeting

Perfect for: Specific host targeting

Common usage: Firewall rules for individual servers

Common usage: Firewall rules for individual servers

Common Private Network Ranges

172.16.0.0/12

Range: 172.16.0.0 - 172.31.255.255Total addresses: 1,048,576Perfect for: Medium to large organizationsCommon usage: Private cloud infrastructures

Range: 172.16.0.0 - 172.31.255.255

Range: 172.16.0.0 - 172.31.255.255

Total addresses: 1,048,576

Total addresses: 1,048,576

Perfect for: Medium to large organizations

Perfect for: Medium to large organizations

Common usage: Private cloud infrastructures

Common usage: Private cloud infrastructures

Public IP Range Example

8.8.8.0/24

Range: 8.8.8.0 - 8.8.8.255Total addresses: 256Example includes: Google's famous DNS server (8.8.8.8)Common usage: Public service networks

Range: 8.8.8.0 - 8.8.8.255

Range: 8.8.8.0 - 8.8.8.255

Total addresses: 256

Total addresses: 256

Example includes: Google's famous DNS server (8.8.8.8)

Example includes: Google's famous DNS server (8.8.8.8)

Common usage: Public service networks

Common usage: Public service networks

Understanding CIDR Numbers: The Key Rule

The CIDR number (the value after the /) works in a counter-intuitive way:

Larger CIDR numbers = Smaller networks/32 = 1 IP address/24 = 256 IP addresses/16 = 65,536 IP addressesSmaller CIDR numbers = Larger networks/8 = 16,777,216 IP addresses/12 = 1,048,576 IP addresses

Larger CIDR numbers = Smaller networks/32 = 1 IP address/24 = 256 IP addresses/16 = 65,536 IP addresses

Larger CIDR numbers = Smaller networks

/32 = 1 IP address/24 = 256 IP addresses/16 = 65,536 IP addresses

/32 = 1 IP address

/32 = 1 IP address

/24 = 256 IP addresses

/24 = 256 IP addresses

/16 = 65,536 IP addresses

/16 = 65,536 IP addresses

Smaller CIDR numbers = Larger networks/8 = 16,777,216 IP addresses/12 = 1,048,576 IP addresses

Smaller CIDR numbers = Larger networks

/8 = 16,777,216 IP addresses/12 = 1,048,576 IP addresses

/8 = 16,777,216 IP addresses

/8 = 16,777,216 IP addresses

/12 = 1,048,576 IP addresses

/12 = 1,048,576 IP addresses

Quick Reference Table



Best Practices

Always plan your CIDR allocations before implementationLeave room for network growth when assigning CIDR blocksDocument your CIDR allocations for future referenceUse appropriate CIDR sizes for your specific needsConsider future expansion when selecting CIDR ranges

Always plan your CIDR allocations before implementation

Always plan your CIDR allocations before implementation

Leave room for network growth when assigning CIDR blocks

Leave room for network growth when assigning CIDR blocks

Document your CIDR allocations for future reference

Document your CIDR allocations for future reference

Use appropriate CIDR sizes for your specific needs

Use appropriate CIDR sizes for your specific needs

Consider future expansion when selecting CIDR ranges

Consider future expansion when selecting CIDR ranges

This guide should help you understand and implement CIDR notation effectively in your network configurations.

[How SealMetrics Blocks Bot Traffic Without Handling IPs](https://help.sealmetrics.com/en/articles/10111680-how-sealmetrics-blocks-bot-traffic-without-handling-ips)[Access Restricted to Authorized IPs](https://help.sealmetrics.com/en/articles/10222135-access-restricted-to-authorized-ips)[SealMetrics Help Center](/en/)Company

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