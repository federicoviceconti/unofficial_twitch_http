# 📦 unofficial_twitch_http

Client package for twitch unofficial app.

Available on pub.dev: https://pub.dev/packages/unofficial_twitch_http

## Features

This package allow to make request using the http's dart package.

For more information see the class [twitch_http_client.dart](lib/twitch_http_client.dart)

## Getting started

The main class [TwitchHttpClient](lib/twitch_http_client.dart) has a concrete implementation
[TwitchHttpClientImpl](lib/twitch_http_client_impl.dart). In order to work, it needs the environment
bundle, where we have to specify the basePath:

```
final client = TwitchHttpClientImpl(
  environmentBundle: EnvironmentBundle(
    basePath: TwitchOpenApiConstants.baseUrl,
  ),
);
```

Then we can make a simple request like:

```
final response = await client.makeGet(
  "/success",
  convertBodyFunc: (response) {
    return MockResult.fromResponse(response);
  },
);
```

All the response are wrapped into the [HttpResult](lib/models/http_result.dart), which contains a
response or eventually an error

## Additional information

If you want a real example, see
the [main app](https://github.com/federicoviceconti/unofficial_twitch_client_flutter)
