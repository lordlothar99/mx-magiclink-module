# Magic Link module for Mendix
MagicLink for auto-signin in Mendix.

Magic links are URLs which allow users to sign in instantaneously, without having to provide their password. Such feature is powerful but might also present a security risk : you'll have to ensure that ONLY the right user can request a magic link, for their own account. Usually magic links are sent by email, as we can consider that it's secure enough.

## Installation

Once this module is imported in your project, you'll have to create a REST endpoint calling the microflow ``Act_AutoSignIn_redirect``, with microflow ``Act_Authenticate`` set for authentication. This REST endpoint is not provided in the module because most developers have a specific way to organize their endpoints. Just open the github project if you need an example.

## Usage

Magic links

## Dependencies

* Community Commons
* REST Deeplink