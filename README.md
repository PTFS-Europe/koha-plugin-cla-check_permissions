# cla-permissions-check-plugin

This is a plugin for [Koha](https://koha-community.org/) that allows you to make queries to the [CLA Check Permissions service](https://www.cla.co.uk/check-permissions-start) for biblios within your catalogue

## Getting Started

At the time of writing (25th June 2018), the Koha core component of this functionality has been [submitted as a bug](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=20968),
but not yet merged into the main product. Until such a time as this is done, in order to use this plugin, you will need to apply Bug 20968 to your Koha installation. This can be done via [git bz](https://wiki.koha-community.org/wiki/Git_bz_configuration)

Once the patch is applied, download this plugin by downloading the latest release .kpz file from the [releases page](https://github.com/PTFS-Europe/cla-permissions-check-plugin/releases).

The plugin system needs to be turned on by a system administrator.

To set up the Koha plugin system you must first make some changes to your install.

Change `<enable_plugins>0<enable_plugins>` to `<enable_plugins>1</enable_plugins>` in your `koha-conf.xml` file
Confirm that the path to `<pluginsdir>` exists, is correct, and is writable by the web server.
Restart your webserver.
Once set up is complete you will need to alter your `UseKohaPlugins` system preference.
Finally, on the "Koha Administration" page you will see the "Manage Plugins" option, select this to access the Plugins page.

### Installing

Once your Koha has plugins turned on, as detailed above, installing the plugin is then a case of selecting the "Upload plugin" 
button on the Plugins page and navigating to the .kpz file you downloaded

### Configuration

**The plugin requires configuration prior to usage**. To configure the plugin, select the "Actions" button listed by the plugin in the "Plugins" page, then select "Configure". On the configure page, you are required to supply your Check Permissions API key, this can be obtained by registering on [the CLA website](https://accountlogin.cla.co.uk/login) and subscribing to the API (this is free). Once you have your key, enter it in the "API Key" field. Also, select which licence most applies to your institution, then click "Save configuration"

### Usage

Once installed, the plugin can be used by navigating to a biblio in your catalogue, on the "Normal" tab, you will see a "CLA Check Permissions" button. This will take you to the CLA Check Permissions page, a request will be made to the API, when the request completes, a modal will be displayed containing the results of the query.



## Authors

* Andrew Isherwood
