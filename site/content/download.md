+++
title = "Download Citra"
advertisement = true
+++

The nightly build of Citra contains already reviewed and tested features. If you require support with the installation 
 or use of Citra, or you want to report bugs you should use this version. This version is still in development, so 
 expect crashes and bugs.

The Canary build of Citra is the same as our nightly builds, with additional features that are still waiting on review 
 before making it into the official Citra builds. We will not provide support for issues found only in this version. If 
 you believe you've found a bug, please retest on our nightly builds. This version is still in development, so expect 
 crashes and bugs.
     
---

<div id="updater-view">
The Citra updater provides a easy interface to install, update and manage Citra. Unless you know what you are doing,
 this is likely what you are looking for.
<br />
<br />

<style>
 .alert {
  padding: 20px;
  background-color: #ff8e03;
  color: white;
  margin-bottom: 15px;
}
 </style>
 
<div class="alert">
  Notice: Citra does NOT support Macs with M1 chipsets. Our Mac builds may run through Rosetta, but you WILL encounter various issues that we won't provide support for. We may eventually support M1 Macs, but not at this time.
</div>
<br />
 
<div class="text-center">
<i id="dl-autodetect">Autodetected platform: XYZ</i>
<br />
<div id="dl-unknown">
    Unknown platform - Citra is <b>only supported</b> on 64-bit versions of Windows, macOS, Linux, and Android 8 (Oreo) or above.
    If you are running one of these, choose one of the options below.
</div>
<a href="https://github.com/citra-emu/citra-web/releases/download/1.0/citra-setup-windows.exe" class="btn btn-lg btn-primary dl-updater-button" id="dl-windows-x64">Download for Windows x64</a>
<a href="https://github.com/citra-emu/citra-web/releases/download/1.0/citra-setup-mac.dmg" class="btn btn-lg btn-primary dl-updater-button" id="dl-mac-x64">Download for Mac x64</a>
<a href="https://flathub.org/apps/details/org.citra_emu.citra" class="btn btn-lg btn-primary dl-updater-button" id="dl-linux-x64">Download for Linux x64</a>
<a href='https://play.google.com/store/apps/details?id=org.citra.citra_emu' class="dl-updater-button" id="dl-android-x64"><img style="width:275px" alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png'/></a>

<br />
<span id="other-container"><a href="#" id="other-platforms-link">Other platforms</a> | </span>
<a href="#" id="manual-link">Manual download</a>
</div>
</div>

<div id="manual-view">
<div class="visible-xs">
  <h3>Citra currently does not support iOS.</h3>
</div>
    
<a href="?" class="btn">Back</a>

<h3>Nightly Build <span style='font-size: smaller; margin-left: 6px;'> Last release was  <span id='last-updated-nightly'></span></span></h3>
<table id="downloads-nightly" class="table">
    <thead>
        <tr>
            <th>Build Date</th>
            <th>Commit Information</th>
            <th>Download</th>
        </tr>
    </thead>
    <tbody>
    </tbody>
</table>
<div style="text-align: center; padding: 0px; margin: 0px;"><a href = "https://github.com/citra-emu/citra-nightly/releases">Click here to view previous versions...</a></div>

<h3>Canary Build <span style='font-size: smaller; margin-left: 6px;'> Last release was  <span id='last-updated-canary'></span></span></h3>
<table id="downloads-canary" class="table">
    <thead>
        <tr>
            <th>Build Date</th>
            <th>Commit Information</th>
            <th>Download</th>
        </tr>
    </thead>
    <tbody>
    </tbody>
</table>
<div style="text-align: center; padding: 0px; margin: 0px;"><a href = "https://github.com/citra-emu/citra-canary/releases">Click here to view previous versions...</a></div>

<h3>Android Build <span style='font-size: smaller; margin-left: 6px;'> Last release was  <span id='last-updated-android'></span></span></h3>
<table id="downloads-android" class="table">
    <thead>
        <tr>
            <th>Build Date</th>
            <th>Commit Information</th>
            <th>Download</th>
        </tr>
    </thead>
    <tbody>
    </tbody>
</table>
<div style="text-align: center; padding: 0px; margin: 0px;"><a href = "https://github.com/citra-emu/citra-android/releases">Click here to view previous versions...</a></div>

<style>
    .table-first { background-color: #fcf8e3; }
    .dl-icon { display: inline-block; border-bottom: 0px !important; }
    .dl-icon img { width: 32px; height: 32px; padding: 4px; }
    .dl-icon img:hover { cursor: pointer; }
</style>
</div>

<div id="no-js-view">
Hi! We see that you have JavaScript disabled. Unfortunately, this means that we cannot automatically
prepare a updater for you, nor are we able to show you the latest archives of Citra either. Here are a few
links to get you started however:<br />
<br />
<a href="https://github.com/citra-emu/citra-web/releases/download/1.0/citra-setup-windows.exe">Windows x64 Installer</a><br />
<a href="https://github.com/citra-emu/citra-web/releases/download/1.0/citra-setup-mac.dmg">Mac x64 Installer</a><br />
<a href="https://flathub.org/apps/details/org.citra_emu.citra">Download for Linux x64</a><br /> 
<a href="https://play.google.com/store/apps/details?id=org.citra.citra_emu">Download for Android</a><br />
<a href="https://github.com/citra-emu/citra-nightly/releases">Nightly Builds</a><br />
<a href="https://github.com/citra-emu/citra-canary/releases">Canary Builds</a> <br />
</div>


<script src="https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.17.1/moment.min.js"></script>
<script type="text/javascript">
    function getRelease(v, count = 5) {
        $.getJSON(`https://api.github.com/repos/citra-emu/citra-${v}/releases`, function(releases) {
            $(`#last-updated-${v}`).text(moment(releases[0].published_at).fromNow());

            for (var i = 0; i < releases.length; ++i) {
                var release = releases[i];
                let release_date = moment(release.published_at).fromNow();

                let release_commit = release.assets[0].name.split('-').pop().trim().split('.')[0];
                let release_commit_url = `https://github.com/citra-emu/citra-${v}/commit/${release_commit}`;

                let release_title = '';
                if (v == 'nightly') {
                    release_title = 'Nightly Build';
                } else if (v == 'canary') {
                    release_title = 'Canary Build';
                } else if (v == 'android') {
                    release_title = 'Android Build';
                }

                if (release_commit) {
                    release_title += ' - ' + release_commit;
                }

                var download_span = '';

                var table_style = '';
                if (i == 0) { table_style = 'table-first'; }

                release.assets.forEach(function(asset) {
                    var is_windows = asset.name.includes('windows') || asset.name.includes('exe');
                    if (asset.name.includes('nupkg')) return;
                    if (asset.name.includes('.aab')) return;
                    if (!is_windows && asset.name.includes('.7z')) return;
                    if (is_windows && asset.name.includes('.tar.gz')) return;
                    if (asset.name.includes('RELEASES')) return;

                    /* We only want to provide mingw builds on the downloads page. */
                    if (asset.name.includes('-msvc-')) return;

                    let env_icon = '/images/icons/file.png';
                    if (is_windows) env_icon = '/images/icons/windows.png';
                    else if (asset.name.includes('osx')) env_icon = '/images/icons/apple.png';
                    else if (asset.name.includes('linux')) env_icon = '/images/icons/linux.png';
                    else if (asset.name.includes('.apk')) env_icon = '/images/icons/android.png';

                    let download_url = `https://github.com/citra-emu/citra-${v}/releases/download/${release.tag_name}/${asset.name}`;
                    download_span += `<a class="dl-icon" href="${download_url}"><img src="${env_icon}"></i></a>`;
                });

                /* Generate the link to the Github release. */
                download_span += `<a class="dl-icon" href="${release.html_url}"><img src="/images/icons/github.png"></i></a>`;

                if (release_commit_url != null) {
                    $(`#downloads-${v}`).append(`<tr class="${table_style}"><td>${release_date}</td>` +
                        `<td><a href="${release_commit_url}">${release_title}</a></td><td>${download_span}</td></tr>`);
                } else {
                    $(`#downloads-${v}`).append(`<tr class="${table_style}"><td>${release_date}</td>` +
                        `<td>${release_title}</td><td>${download_span}</td></tr>`);
                }
                if (i + 1 >= count) { break; }
            };
        });
    }
    
    function fetchReleases() {
        getRelease('nightly');
        getRelease('canary');
        getRelease('android');
    }
    
    // Attempt autodetection of their operating system
    var userAgent = navigator.userAgent.toLowerCase();
    
    var allPlatforms = ["windows", "mac", "linux", "android"];
    
    var os = undefined;
    if (userAgent.indexOf("windows") !== -1) {
        os = "Windows";
    } else if (userAgent.indexOf("mac") !== -1 && userAgent.indexOf("mobile") === -1 && userAgent.indexOf("phone") === -1) {
        os = "Mac";
    } else if (userAgent.indexOf("linux") !== -1 && userAgent.indexOf("android") === -1) {
        os = "Linux";
    } else if (userAgent.indexOf("android") !== -1) {
        os = "Android";
    }
    
    if (os !== undefined) {
        $("#dl-" + os.toLowerCase() + "-x64").css("display", "block");
        
        var autodetect = $("#dl-autodetect");
        autodetect.text("Autodetected platform: " + os);
        autodetect.css("display", "inline");
    } else {
        $("#dl-unknown").css("display", "block");
    }
    
    $("#no-js-view").css("display", "none");
    $("#updater-view").css("display", "block");
    
    $("#other-platforms-link").click(function() {
        for (var i = 0; i < allPlatforms.length; i++) {
            var platform = allPlatforms[i];
            $("#dl-" + platform + "-x64").css("display", "block");
            $("#other-container").css("display", "none");
        }
    });
    
    $("#manual-link").click(function() {
        $("#updater-view").css("display", "none");
        $("#manual-view").css("display", "block");
        fetchReleases();
    });
</script>
