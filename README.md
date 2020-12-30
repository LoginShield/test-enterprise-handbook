Enterprise Test Environment Handbook
====================================

To run the test environment locally, you'll need to:

1. Follow directions in [test-enterprise-service-node-js](https://github.com/LoginShield/test-enterprise-service-node-js) to start the service API locally at `http://localhost:7101/service`
2. Follow directions in [test-enterprise-website-html5](https://github.com/LoginShield/test-enterprise-website-html5) to start the website locally at `http://localhost:7102/`
3. Follow directions in [http-proxy-node-js](https://github.com/jbuhacoff/http-proxy-node-js) to start the proxy locally at `http://localhost` using the `test_enterprise_localhost.json` file from this repository

Then you can browse to `http://localhost` to interact with it.

The proxy configuration directs all requests starting with `/service`
to the `test-enterprise-service-node-js` project running on port 7101,
and all other requests to the `test-enteprise-website-html5` project
running on port 7102.

# Local testing workaround

When you are testing locally, you will notice that login requests are
rejected by the production LoginShield service, because it only allows
realms with `https` URLs.

You can use the following procedure to resolve the issue and continue
testing locally:

If you already have a realm configured in
LoginShield, you can use the same Endpoint URL, Realm Id, and Realm
Authorization Token as you would in production.

Then, when you get the
safety notice in the LoginShield app, choose the "email" method to
continue.

When you get the email with the login link, do not follow
the link -- instead, copy the link somewhere you can edit it, and
replace the production Endpoint URL at the beginning of the link with
`http://localhost`, so the link looks like `http://localhost/login?...`
and then paste the modified link into your browser.

Subsequent logins to `http://localhost` should not trigger the safety
notice and you won't need to do any more editing like that unless you
clear your browser cache or reset your authenticator.
