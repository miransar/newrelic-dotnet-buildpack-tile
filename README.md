---
# New Relic Dotnet Extension Buildpack for PCF (General Access)

---

<br/><br/>

This document describes [New Relic Dotnet Extension Buildpack Tile for VMware Tanzu (PCF)](https://network.pivotal.io/products/new-relic-dotnet-buildpack/) and instructions on how to install and use New Relic's Dotnet extension tile to bind New Relic agents to Dotnet Core or Dotnet Framework applications to monitor them in [VMware Tanzu](https://tanzu.vmware.com/tanzu) (PCF) environment.

<br/>

<p align="center">
    <img src="images/NR_logo_256x296.png" alt="New Relic Dotnet Extension Buildpack" height="150" width="150"/>
</p>

<br/>


## <a id='overview'></a> Overview

New Relic Dotnet Extension Buildpack for PCF enables you to bind your Dotnet (Core and Framework) applications to New Relic Dotnet agents, and monitor the health and performance of these applications, analyze the data captured by agents, and aditionally correlate the captured agent data with PCF infrastructure which is collected by [New Relic Firehose Nozzle](https://network.pivotal.io/products/nr-firehose-nozzle/).

The extension buildpacks could be installed using the tile in OpsMgr, or alternatively you could extract the <strong>".pivotal"</strong> file, and install individual extension buildpack(s) using CF CLI command <strong>"cf create-buildpack"</strong> as you wish. 

Once you start monitoring your applications, you would also have the ability to set alerts based on any metrics that are collected by Dotnet agents using New Relic's alerting subsystem.


The tile installs one or more of the following 4 buildpacks depending on the tile configuration:

1. New Relic Dotnet Core Extension Buildpack for Dotnet Core Applications (Ubuntu Trusty & xenial)
1. New Relic Dotnet Core Extension Cached Buildpack for Dotnet Core Applications (Ubuntu Trusty & xenial) running in disconnected (isolated) PCF deployments
1. New Relic HWC  Extension Cached Buildpack for Dotnet Framework Applications (Windows 2012 R2 & Windows 2016)
1. New Relic HWC  Extension Buildpack for Dotnet Framework Applications (Windows 2012 R2 & Windows 2016) running in disconnected (isolated) PCF deployments

The first 2 extension buildpacks are for Dotnet Core applications running on Ubuntu Trusty (14.04) and Ubuntu Xenial (16.04). The first extension is non-cached, and the second one is cached version of buildpack for Dotnet Core.

The 3rd and 4th buildpacks are HWC extensions for Windows 2012 R2 and Windows 2016. The third extension is non-cached, and the fourth one is cached version of HWC extension buildpacks.

All 4 buildpacks use the multi-buildpack approach of Cloud Foundry and require either the standard Dotnet Core buildpack or HWC buildpack to be specified in the buildpack chain, either in application's manifest or in the CF CLI command line.

</p>
<p class="note"><strong>Note:</strong> The cached version of this extension buildpack for both Dotnet Core and Dotnet Framework contains New Relic Dotnet Agents version <code>8.27.139.0</code></p>


<br/>


## <a id="snapshot"></a> Product Snapshot

The following table provides version and version-support information about New Relic Dotnet Extension Buildpack for PCF.

<table class="nice">
    <th>Element</th>
    <th>Details</th>
    <tr>
        <td>Tile version</td>
        <td>1.1.11</td>
    </tr>
    <tr>
        <td>Release date</td>
        <td>June 24, 2023</td>
    </tr>
    <tr>
        <td>Software component version</td>
        <td>New Relic Dotnet Extension Buildpack v1.1.11 (General Access)</td>
    </tr>
    <tr>
        <td>Compatible Ops Manager version(s)</td>
        <td>v2.9.x, v2.10.x and v3.0.x</td>
    </tr>
    <tr>
        <td>Compatible Pivotal Application Service versions</td>
        <td>v2.10.x, v2.11.x, v2.12.x, v2.13.x, v3.0.x and v4.0.x</td>
    </tr>
    <tr>
        <td>IaaS support</td>
        <td>AWS, GCP, Azure, and vSphere</td>
    </tr>
</table>


## <a id='compatibility'></a> Compatibility

This product has been tested and is compatible with PCF versions v2.1.x and above.


## <a id="reqs"></a> Requirements

As prerequisite you need to have the following
* An active New Relic account with a license key which is used to bind Dotnet applications to New Relic Dotnet agents.
* In order to use [multi-buildpacks in the application's manifest file](https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html#buildpack), at a minimum you need to upgrade CF CLI to <strong>version 6.38</strong>.
* Dotnet HWC extension requires a minimum version of hwc buildpack 3.0.3.
* Dotnet Core extension requires a minimum version of dotnet core buildpack 2.1.5.


## <a id='trial'></a> Trial License

If you do not already have a New Relic account, you can obtain an account with a [trial license](http://newrelic.com/signup?funnel=pivotal-cloud-foundry&partner=Pivotal+Cloud+Foundry).


## <a id="feedback"></a> Feedback

If you have feature requests, questions, or information about a bug, please submit an issue [on github](https://github.com/newrelic/newrelic-dotnet-buildpack-tile/issues).

<br/><br/><br/>
---
---
---
---
