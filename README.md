# Deprecation Notice

This fork was originally created to allow use of shallow Radar clone and maintain metadata, in the `hathway` fork. Rather than update to include privacy manifest support as part of mParticle's [8.1.0 release](https://github.com/mparticle-integrations/mparticle-apple-integration-radar/releases/tag/v8.1.0), which includes Radar's [3.9.14 release](https://github.com/radarlabs/radar-sdk-ios/releases/tag/3.9.14), the fork has been retired.

The `hathway` fork [maintained metadata](https://github.com/hathway/mparticle-apple-integration-radar/commit/e4e31ac15d8c5b5de2b716514b65b61eaba56f8d), this can be done by getting and setting the Radar metadata around starting the kit:

```
        var radarMetadata = Radar.getMetadata() ?? [:]
        MParticle.sharedInstance().start(with: mParticleOptions)
        radarMetadata.merge(Radar.getMetadata() ?? [:]) { (_, new) in new }
        Radar.setMetadata(radarMetadata)
```

---

## Radar Kit Integration

This repository contains the [Radar](https://www.radar.io) integration for the [mParticle Apple SDK](https://github.com/mParticle/mparticle-apple-sdk).

### Adding the integration

1. Add the kit dependency via SPM or to your app's Podfile or Cartfile:

    ```
    pod 'mParticle-Radar', '~> 8.0'
    ```

    OR

    ```
    github "mparticle-integrations/mparticle-apple-integration-radar" ~> 8.0
    ```

2. Follow the mParticle iOS SDK [quick-start](https://github.com/mParticle/mparticle-apple-sdk), then rebuild and launch your app, and verify that you see `"Included kits: { Radar }"` in your Xcode console 

> (This requires your mParticle log level to be at least Debug)

3. Reference mParticle's integration docs below to enable the integration.

### Documentation

[Radar integration](https://docs.mparticle.com/integrations/radar/event/)

### License

[Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)
