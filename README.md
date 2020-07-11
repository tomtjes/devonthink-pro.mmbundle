# Configuration

This bundle will not work out of the box. You need to go to the `Commands` folder (on Mac, right-click the bundle > `Show Package Contents`) and edit the files in a text editor.

The `SampleGroup.mmCommand` file looks like this:
```
{
	name          = 'SampleGroup';
	input         = 'raw';
	environment   = 'MM_DT_DATABASE_PATH=/Users/MyName/Databases/MyDatabase.dtBase2\nMM_SUBJECT=${subject.prefix:+${subject.prefix} }${subject.blob:+[${subject.blob}] }${subject.body:no subject}\nMM_MESSAGE_ID=${message-id.split}\n';
	command       = '#!/bin/bash\n"${MM_BUNDLE_SUPPORT}/bin/add-to-group"';
	keyEquivalent = "";
	uuid          = '32FB82FD-E643-4509-BD24-C1E9EDE2CFC0';
}
```
Set `name` to the name of the group in DevonThink that the emails will be imported to.
In the `environment` line you need to adjust the path to the DevonThink database. Don't change anything after the first `\n`.
For each DevonThink group that you want to file emails into, you need to create another `.mmCommand` file. If you use more than the two sample commands included, you also need to adjust the `uuid` value so that each `.mmCommand` has a unique UUID. ([How to create a UUID](https://github.com/mailmate/mailmate_manual/wiki/Bundles#uuid))

# Installation

Follow [these instructions](https://github.com/mailmate/mailmate_manual/wiki/Bundles#customizing-a-default-bundle) and adjust the Github URL to this bundle's repository.

# License

If not otherwise specified (see below), files in this repository fall under the following license:

	Permission to copy, use, modify, sell and distribute this
	software is granted. This software is provided "as is" without
	express or implied warranty, and with no claim as to its
	suitability for any purpose.

An exception is made for files in readable text which contain their own license information, or files where an accompanying file exists (in the same directory) with a “-license” suffix added to the base-name name of the original file, and an extension of txt, html, or similar.
