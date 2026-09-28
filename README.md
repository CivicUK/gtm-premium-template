# Civic Cookie Control Premium — Google Tag Manager Template

This Google Tag Manager custom template integrates **Civic Cookie Control Premium** with Google Tag Manager and configures **Google Consent Mode** for your website.

The template sets a default consent state before loading Cookie Control Premium, then allows the consent management platform to manage the visitor's consent choices.

## Features

* Loads Civic Cookie Control Premium from the official Civic CDN.
* Configures Google Consent Mode default consent states.
* Sets the Civic Google developer ID.
* Supports Consent Mode signals including:

  * `ad_storage`
  * `analytics_storage`
  * `ad_user_data`
  * `ad_personalization`
  * `functionality_storage`
  * `personalization_storage`
  * `security_storage`
* Uses Google Tag Manager's sandboxed APIs for consent configuration and script loading.
* Restricts external script loading to Civic's CDN.

## Requirements

Before using this template, you will need:

* A Google Tag Manager web container.
* A Civic Cookie Control Premium account.
* A Cookie Control API key.
* A Cookie Control domain key.

## Installation

1. Open your Google Tag Manager web container.
2. Go to **Templates**.
3. Under **Tag Templates**, select **Search Gallery**.
4. Search for **Civic Cookie Control Premium**.
5. Add the template to your workspace.
6. Create a new tag using the **Civic Cookie Control Premium** template.
7. Enter your Cookie Control API key.
8. Enter your Cookie Control domain key.
9. Set the tag to fire on **Consent Initialization – All Pages**.
10. Submit and publish your container when you have completed testing.

The template should run as early as possible in the page lifecycle so that the default Consent Mode state is established before other tags evaluate consent.

## Configuration

### API key

Enter the API key provided by Civic for your Cookie Control Premium implementation.

### Domain key

Enter the domain key associated with the website on which Cookie Control is being deployed.

These values are provided as part of your Civic Cookie Control configuration and can be found within the Cookie Control user area.

## Consent Mode

The template establishes the following default Consent Mode state:

| Consent type              | Default   |
| ------------------------- | --------- |
| `ad_storage`              | `denied`  |
| `analytics_storage`       | `denied`  |
| `ad_user_data`            | `denied`  |
| `ad_personalization`      | `denied`  |
| `functionality_storage`   | `denied`  |
| `personalization_storage` | `denied`  |
| `security_storage`        | `granted` |

A `wait_for_update` value of 2000 milliseconds is used to allow the consent management platform time to obtain or update the visitor's consent state before tags that depend on consent continue processing.

The template establishes the **default** state. The visitor's subsequent consent choices are handled by the Cookie Control implementation.

## Recommended trigger

For web containers, configure the tag to fire using:

**Consent Initialization – All Pages**

This ensures that the default consent state is established before other tags run.

Do not use a later page-view trigger for the initial consent configuration, as this can allow other tags to evaluate consent before the default state has been established.

## Testing

Before publishing, test the template in Google Tag Manager's Preview mode and verify that:

1. The Cookie Control script loads successfully.
2. The expected Cookie Control configuration is loaded.
3. Consent Mode defaults are established before other relevant tags run.
4. Tags requiring consent respond correctly to the default denied state.
5. Accepting or rejecting categories through Cookie Control produces the expected consent behaviour.
6. Existing consent choices are handled correctly on subsequent page loads.

You should also test the implementation in the browsers and environments supported by your website.

## Permissions

The template uses Google Tag Manager's sandbox APIs to:

* Set Consent Mode default states.
* Set the Civic developer ID.
* Inject the Cookie Control script from Civic's CDN.

The template does not provide arbitrary third-party script loading. The external script permission is restricted to the Civic Cookie Control CDN.

## Data and privacy

This template is intended to provide the Google Tag Manager integration for Civic Cookie Control Premium.

The template itself does not collect or store visitor consent records independently. Consent management and the presentation of the Cookie Control interface are provided by the Civic Cookie Control service.

Your site's privacy and cookie policies should accurately describe the services and tags deployed through your Google Tag Manager container.

## Support

For questions about:

* Cookie Control Premium configuration
* API keys or domain keys
* Cookie Control functionality
* Your Civic account
* Consent management configuration

please refer to Civic's Cookie Control documentation or contact Civic support.

Read more at https://cookiecontrol.com/docs/premium

For questions about Google Tag Manager's template system or Consent Mode, refer to Google's official documentation.

## Development

This repository contains the source for the Civic Cookie Control Premium Google Tag Manager custom template.

Changes to the template should be tested in Google Tag Manager before being released.

## Licence

This project is licensed under the Apache License 2.0.