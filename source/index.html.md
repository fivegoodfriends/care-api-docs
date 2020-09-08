---
title: Lookout App API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

> Endpoint:

```shell
https://app.fivegoodfriends.com.au/care/api
```

Welcome to the Lookout App API! This API is very VERY early in the development process, you can't really use it yet :)

We provide code examples in shell (for now). You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Versioning

> Versions:

```shell
https://app.fivegoodfriends.com.au/care/api/v1/
```

Add the version of the API to the end of the base URL. In this case `v1`. For now this is the only version.


# Authentication

> To authorize, use this code:

```shell
curl https://endpoint \
  -H "Authorization: Token token=ToKeNgOeShErE"
```

> Make sure to replace `ToKeNgOeShErE` with your user API key.

The API uses an API key per user to allow access. You can get an API key from the authentication API for the logged in user (coming soon).

Lookout expects the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Token token=ToKeNgOeShErE`

<aside class="notice">
You must replace <code>ToKeNgOeShErE</code> with your user API key.
</aside>

# Headers

> To provide the appropriate headers, use this code:

```shell
curl https://endpoint \
  -H "User-Agent: Client.App.Name. for iOS 1.0 (000), id com.client-app-name.app, iPhone 14.0.0" \
  -H "Accept-Encoding: gzip, deflate" \
  -H "Accept: application/json" \
  -H "Authorization: Token token=ToKeNgOeShErE"
```

A consistent user agent should be provided for your client app or service.

The app can vend zipped content so your app should specify that it can accept this.

JSON will be returned from the API, unless otherwise stated, so your app should specify this is acceptable.

# Profile Avatars

This endpoint allows the setting and getting of profile avatars.


## Fetch Avatar for a Specific Profile

```shell
curl "https://app.fivegoodfriends.com.au/care/api/v1/profiles/<PROFILE_ID>/avatar"
  -H "Authorization: Token token=ToKeNgOeShErE"
```

> The above command returns JSON structured like this:

```json
{
  "url": "https://res.cloudinary.com/fgf/image/upload/somethings/v1/avatar/img.jpg"
}
```

This endpoint retrieves the URL to an avatar for a specific profile. You can then use this URl from an external service to display the avatar image.

### HTTP Request

`GET https://app.fivegoodfriends.com.au/care/api/v1/profiles/<PROFILE_ID>/avatar<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
PROFILE_ID | The ID of the profile


## Replace Avatar for a Specific Profile

```shell
curl "https://app.fivegoodfriends.com.au/care/api/v1/profiles/<PROFILE_ID>/avatar"
  -X PUT
  -H "Authorization: Token token=ToKeNgOeShErE"
  -H 'Content-Type: image/jpeg'
  -d <IMAGE_DATE>
```

> The above command returns JSON structured like this:

```json
{
  "url": "https://res.cloudinary.com/fgf/image/upload/somethings/v1/NEW_avatar/NEW_img.jpg"
}
```

This endpoint adds the provided image as an avatar to the given Profile ID, replacing the existing avatar.

<aside class="notice">
You must provide a header describing the type of image. JPEG, PNG, GIF are accepted.
</aside>

### HTTP Request

`PUT https://app.fivegoodfriends.com.au/care/api/v1/profiles/<PROFILE_ID>/avatar`

### URL Parameters

Parameter | Description
--------- | -----------
PROFILE_ID | The ID of the profile

### Body

The body should contain the avatar image.
