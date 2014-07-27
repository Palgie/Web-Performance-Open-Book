RUM & Synthetic
=====================================

While making changes to your website(s) without understanding the direct benefit to your end user is ambitious it should be avoided. Even the most common of best practices could hinder performance if applied incorrectly. Merging some of your content into a single file for example is a great way to reduce HTTP calls but if you're merging large amounts of content that aren't even present for another 3-4 pages down your critical path do you really need these as a blocking asset on your landing page? Understanding how changes effect your customers as a whole is important. Test early and test often.

## RUM

RUM (Real User Monitoring) is the most common type of monitoring as it's more accurate to how your users experience your website(s). Rather than just testing that you or your colleague experience a site quicker in your Chrome browser, the collection of RUM metrics will give you more of an indication if the majority have a greater experience.

## Synthetic

While Real User Monitoring is a very effective way to measure your performance effectively there is still some good value to be had from Synthetic testing. Unlike Real User Monitoring a synthetic test tends to happen in a controlled environment. You can specify multiple types of scenarios in which you'd like to test. This allows you to remove many uncontrollable variables that changing so aggressively - The network connection for example. This control over the environment allows you to understand quickly how your user _might_ experience a change you've made. As the results of a synthetic test are usually fairly static it acts as a really quick feedback loop for you or your colleagues to see performance regressions before they're released into production.

Using both techniques to understand change and how your website(s) perform in a real world environment will help you and your team become less reactive and more effective and proactive with performance improvements.