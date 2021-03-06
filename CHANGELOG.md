# Change Log for aws-lambda-ses-forwarder

## 3.1.0 [2016/9/24]

- Adding `subjectPrefix` configuration for adding a prefix string to the subject
of forwarded email.
- Updating regex match for the Reply-To header to be case insensitive to support
email sent with a Reply-to header.
- Fixing how libraries are loaded to improve performance.

## 3.0.0 [2016/5/14]

- Adding capability to specify an email forwarding mapping that acts as a
wildcard or catch-all for a domain.
- Converting the inbound recipient email address to lowercase before comparing
to the forwarding map to handle case variations.
- Updating aws-sdk dependency to match AWS Lambda environment.

### Upgrade Notes

- Email addresses and domain wildcard keys in the `forwardMapping` configuration
object must be lowercase.

## 2.3.0 [2016/4/21]

- Adding configuration option for a static "From" email address.

## 2.2.0 [2016/3/30]

- Removing all DKIM-Signature headers to prevent errors when forwarding or DKIM
verification issues when received.
- Updating the email processing to remove any Sender header and to only add a
Reply-To header if one does not already exist.

## 2.1.0 [2016/3/22]

- Allowing the log function to be overridden.
- Reworking log output as structured data.

## 2.0.0 [2016/3/16]

- Major refactor for configurability and testability.
- Adding test coverage with Mocha and Istanbul and configuration for eslint.
- Removing DKIM-Signature headers for the amazonses.com domain to prevent error
when forwarding.
- Improving format of modified From header.
- Adding documentation and example for implementing this module.

## 1.0.2 [2016/2/23]

- Ensuring empty lines are not left when the headers are altered.
- Removing any Return-Path headers.

## 1.0.1 [2015/12/3]

- Removing any Reply-To headers to prevent conflicts with the new headers added.

## 1.0.0 [2015/11/2]

- Initial release of aws-lambda-ses-forwarder.
