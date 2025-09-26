<div align="center">
  <img alt="rumqtt Logo" src="docs/rumqtt.png" width="60%" />
</div>
<br/>

# About this fork

This fork is a fork of [rumqtt](https://github.com/bytebeamio/rumqtt)with support for FIDO2 client authentication through a modified version of the rustls TLS library.
For this the rumqttd binary was modified to use the modified [tokio-rustls](https://github.com/7ritn/tokio-rustls#) library, which in turns uses a [rustls fork](https://github.com/7ritn/rustls) that supports FIDO2 client authentication.
To test this a USB attached FIDO2 device is required.

The rumqtt daemon can be configured using environment variables.

| Variable Name                   | Description                            | Default Value                 | Example Value                     |
|---------------------------------|----------------------------------------|-------------------------------|-----------------------------------|
| `FIDO_RP_ID`                    | FIDO Relying Party ID                  | `localhost`                   | `example.com`                     |
| `FIDO_RP_NAME`                  | FIDO Relying Party Name                | `localhost`                   | `Example Inc.`                    |
| `FIDO_USER_VERIFICATION`        | FIDO user verification policy          | `Preferred`                   | `Required`                        |
| `FIDO_AUTHENTICATOR_ATTACHMENT` | FIDO authenticator attachment          | `CrossPlatform`               | `Platform`                        |
| `FIDO_TIMEOUT`                  | FIDO timeout in milliseconds           | `60000`                       | `30000`                           |
| `FIDO_TICKET`                   | FIDO ticket as comma-separated bytes   | `4,3,2,1`                     | `1,2,3,4`                         |
| `FIDO_MANDATORY`                | Make FIDO authentication mandatory     | `true`                        | `false`                           |
| `FIDO_DB_PATH`                  | Path to the FIDO database file         | `./fido.db3`                  | `/var/lib/fido.db3`               |

For a client example see [rumqtt-fido-client](https://github.com/7ritn/rumqtt-fido-client).

# License

This project is released under The Apache License, Version 2.0 ([LICENSE](./LICENSE) or http://www.apache.org/licenses/LICENSE-2.0)
