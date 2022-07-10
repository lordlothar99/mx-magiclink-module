# Magic Link module for Mendix

MagicLink for auto-signin in Mendix.

Magic links are URLs which allow users to sign in instantaneously, without having to provide their password. Such feature is powerful but might also present a security risk : you'll have to ensure that ONLY the right user can request a magic link, for their own account. Usually magic links are sent by email, as we can consider that it's secure enough.

Magic link can be displayed as a QR code in your frontoffice thanks to this module : https://marketplace.mendix.com/link/component/2891

## Installation

1. Import the module in your project
2. Create a REST endpoint calling the microflow ``Act_AutoSignIn_redirect``, with microflow ``Act_Authenticate`` set for authentication. This REST endpoint is not provided in the module because most developers have a specific way to organize their endpoints. Just open the github project if you need an example.
3. Add a way to generate a Magic link in your app, by calling ``Act_GenerateMagicLink``. ``ValidityMinutes`` attribute can be used for automatic expiry, and ``MaxUsages`` attribute allows you to restrict the number of times the Magic link is used. Empty values are allowed for both (but not recommended).
4. Ensure old Magic links are purged using the microflow ``Act_PurgeInvalidMagicLinks`` ; a scheduled event is provided : ``ScE_PurgeInvalidMagicLinks``

## Example

Example can be found in Github project : download, and run locally.
You'll find the configuration of the REST endpoint and the QR code generation.

## Mendix version

* 9+

## Dependencies

* Community Commons
* REST Deeplink
