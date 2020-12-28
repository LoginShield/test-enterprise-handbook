Enterprise Test Environment Handbook
====================================

The service does NOT use a database; all data is stored in memory so
every time it starts the tests can be repeated.

To run the test environment locally, you'll need to:

1. Follow directions in [test-enterprise-service-node-js](https://github.com/LoginShield/test-enterprise-service-node-js) to start the service API locally at `http://localhost:7101/service`
2. Follow directions in [test-enterprise-website-html5](https://github.com/LoginShield/test-enterprise-website-html5) to start the website locally at `http://localhost:7102/`
3. Follow directions in [http-proxy-node-js](https://github.com/jbuhacoff/http-proxy-node-js) to start the proxy locally at `http://localhost` using the `test_enterprise_localhost.json` file from this repository
