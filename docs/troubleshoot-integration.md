---
title: Troubleshoot your integration
---

import useBaseUrl from '@docusaurus/useBaseUrl';

After you've added the Plausible Analytics script to your website, it's time to verify that the integration is working.

In your Plausible Analytics account, click on your site domain name. You should see a blinking green dot which indicates that we’re listening for incoming page views in real-time. You can visit your site and the dashboard will update instantly with your visit.

<img alt="Listening for incoming page views" src={useBaseUrl('img/waiting-for-pageview.png')} />

Once the first page view comes through, you'll be automatically taken to the stats dashboard. There are no delays in the data. The dashboard goes live and displays the data as soon as the first visitor is counted.

If you didn't see the green blinking dot, there's nothing to worry about. It just means that someone visited your site already since you installed the Plausible Analytics script.

If you see the dashboard with graphs and numbers, it means everything is working! Congrats! Plausible Analytics is now tracking your website statistics while preserving the privacy of your visitors.

## Keep seeing a blinking green dot?

Do you keep seeing a blinking green dot screen despite having visitors on your site? Please verify if our script is installed correctly.

You can load your website, open the browser inspector (press F12 on Firefox or Chrome), and ensure that the Plausible Analytics script is loading in the "Network" tab.

<img alt="Ensure that the Plausible Analytics script is loading in the 'Network' tab" src={useBaseUrl('img/dev-tools-troubleshoot.png')} />

Alternatively, you can verify this by viewing the HTML of your site in your browser. Visit your site, right-click anywhere on the page and choose "**View Page Source**". Then press `cmd+f` on a Mac or `ctrl+f` on Linux and Windows to search. Type `plausible` to search for the Plausible Analytics script.

### Is Plausible script not installed on your site?

You should see the Plausible Analytics tracking script in the source code of your website. If you cannot see the script, please double check if you've inserted it correctly. Installing Plausible on a site can be a slightly different process depending on what tools you're using.

We've put together several integration guides that cover popular website builders and content management systems (CMS) such as WordPress and Ghost. Thanks to the members of our community, there are also community integrations and plugins for several frameworks such as Hugo and GatsbyJS. These can help you set up and start counting your site visitors in no time.

Here's [the full list of all integrations and guides](integration-guides.md).

### Plausible script is on your site but still seeing the green blinking dot and no stats?

* Please ensure that the script you use is exactly the same script as listed in your website settings. You can find your JavaScript snippet by [logging into your Plausible account](https://plausible.io/sites). Here you'll find the list of sites you've added to Plausible. Hover over your site name and click on the "**Settings**" icon on the right hand side of the domain name you'd like to get the snippet for. Then scroll down to the "**Javascript snippet**" section on the following page.

* Are you using a Content Security Policy? Do not forget to add our domain specifically to your CSP.

* Running on localhost? Our script automatically disables itself when running on localhost as the majority of people don't want those stats to be counted.

* Using cache? Do purge the cache just in case.

## Would you like to exclude your own visits from being tracked?

You can do so by following the instructions [in this guide](excluding.md).

On WordPress? [Our Wordpress plugin](https://plausible.io/wordpress-analytics-plugin) excludes admin visits by default.

## Running an adblocker that blocks the Plausible script from being loaded?

If you're running an adblocker or if you're concerned about adblockers, you can enable our custom domain integration which allows you to run the Plausible script as a first-party connection from your domain name. [See the instructions here](custom-domain.md).

## Do you see wrong data in your countries report?

Are you using Cloudflare and having your sites proxied? A proxy can override the remote IP which would lead to wrong geolocation data in your stats. Remove the proxy and make it just a DNS record in your Cloudflare settings to solve the issue.
