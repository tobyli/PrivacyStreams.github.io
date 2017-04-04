---
layout: homepage
title: Installing Dropbox service.
---

If you are developing a data collector, PrivacyStreams offers a convenient feature:
directly uploading the collected data to your Dropbox (using `DropboxOperators.uploadTo` APIs).

To use Dropbox APIs, you need to install Dropbox library in your app. Specifically:
 
First, add Dropbox SDK dependency to `build.gradle`.

<pre>
<code>dependencies {
    compile 'com.github.privacystreams:privacystreams-core:0.0.4'</code>
    <code class="highlight">compile 'com.dropbox.core:dropbox-core-sdk:2.1.1'</code>
    <code>...
}</code>
</pre>

Then set Dropbox global configurations.

<pre>
<code>protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        Globals.DropboxConfig.accessToken = "your dropbox access token";  // Get your token from https://www.dropbox.com/developers
        Globals.DropboxConfig.leastSyncInterval = 30*60*1000;  // Set the interval of uploading (30min in this example).
        Globals.DropboxConfig.onlyOverWifi = false;  // Set whether to upload data only over WIFI. 
        ...
}</code>
</pre>