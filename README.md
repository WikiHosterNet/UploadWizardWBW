# UploadWizardWBW
Provides extra licenses to the UploadWizard extension used by WürzburgWiki

## LocalSettings.php

```php
// Register module
$wgResourceModules['wbwUploadWizardResources'] = [
	'styles' => [
		'extensions/UploadWizardWBW/wbwUploadWizard.css'
	],
	'messages' => [
		'mwe-upwiz-license-cc-by-nc-sa-3.0-de',
		'mwe-upwiz-license-wbw-head',
		'mwe-upwiz-license-wbw',
		'mwe-upwiz-license-logo',
		'mwe-upwiz-license-public-domain-head',
		'mwe-upwiz-license-public-domain-subhead',
		'mwe-upwiz-license-pd-old-1959',
		'mwe-upwiz-license-pd-old-1930',
		'mwe-upwiz-license-coa',
		'mwe-upwiz-license-free'
	],
];

// Load messages
$wgMessagesDirs['wbwUploadWizardResources'] = 'extensions/UploadWizardWBW/i18n';

// Set hook
function wbwUploadWizardResourcesLoader( &$out ) {
	$out->addModules( 'wbwUploadWizardResources' );
	return true;
}

// Register hook
$wgHooks['BeforePageDisplay'][] = 'wbwUploadWizardResourcesLoader';
```
## Note

The UploadWizard extension needs to be installed and configured to require additional licenses which in turn require the system messages and the icon file provided with this code.

## TODO

- Turn this into an actual extension to declutter "LocalSettings.php".
- Translate system messages into English.
