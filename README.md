# remote_transmitter
Temporary remote_receiver component for Esphome

When using a remote_transmitter in an ESP32-C3 project the receiver must be on channel 0 or 1. (for ESP32-S3 0,1 or 3 mentioned by @RENOxDECEPTION) The current Esphome code has no option for configuring that.
This is a quick hack to go around this issue. Until Esphome includes an option to configure the channel, include this external component in your Esphome config.
The rmt_channel is 4 based. So to use the 0 channel, specify "rmt_channel: 0"

```yaml
external_components:
  - source: github://predam/remote_transmitter
    components: [ remote_transmitter ]

remote_transmitter:
  pin:
    number: 3
  rmt_channel: 2
  dump: all
```

Ref: https://github.com/esphome/issues/issues/2934
Inspired by: https://github.com/Jorre05/remote_receiver 
