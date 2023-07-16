# SSL Renegotation failure demo

To see the failure, you have to be on the NIH network (e.g., behind the firewall). Then:

1. [Install NodeJS](https://nodejs.org/en) (version 18 or greater).
1. Clone this repository.
1. In this repository's directory, perform an `npm install`.

You should see NPM try to install the single dependency, and then after a delay, error out with an error similar to:

```
npm ERR! code EPROTO
npm ERR! syscall write
npm ERR! errno EPROTO
npm ERR! request to https://codeload.github.com/NCI-CCR-OIT/node-openid-client/tar.gz/ae845ec8c9cd97830d51733f239cba70eca32cc6 failed, reason: write EPROTO 009E0BF301000000:error:0A000152:SSL routines:final_renegotiate:unsafe legacy renegotiation disabled:../deps/openssl/openssl/ssl/statem/extensions.c:922:
npm ERR!
```

This only happens when on the NIH network; it appears to be related to SSL interception.
