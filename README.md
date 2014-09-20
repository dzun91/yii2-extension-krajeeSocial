yii2-extension-krajeeSocial
===========================

A Yii2 Solr Extension is customized from [Krajee's social](http://demos.krajee.com/social) for my Yii2's structure

Module that enables access to social plugins for Yii Framework 2.0. It includes support for embedding plugins from the following networks into your website:

- Disqus
- Facebook  
  - Like Button
  - Share Button
  - Send Button
  - Embedded Posts
  - Follow Button
  - Comment Button
  - Activity Feed
  - Recommendations Feed
  - Recommendations Bar
  - Like Box
  - Face Pile
- Google Plus
  - Signin Plugin
  - +1 Button
  - Share Button
  - Follow Button
  - Page Badge
  - Person/Profile Badge
  - Community Badge
  - Embedded Posts
- Google Analytics
- Twitter
  - Share Button
  - Follow Button
  - Hash Tag Button
  - Mention Button
  - Embedded Posts/Tweets
- GitHub
  - Watch Button
  - Fork Button
  - Follow Button

## Usage

### Module Configuration
You can view [usage and demos](http://demos.krajee.com/social) on the module.

```php
'modules' => [
    'social' => [
        // the module class
        'class' => 'extensions\krajeeSocial\Module',

        // the global settings for the disqus widget
        'disqus' => [
            'settings' => ['shortname' => 'DISQUS_SHORTNAME'] // default settings
        ],

        // the global settings for the facebook plugins widget
        'facebook' => [
            'appId' => 'FACEBOOK_APP_ID',
            'secret' => 'FACEBOOK_APP_SECRET',
        ],

        // the global settings for the google plugins widget
        'google' => [
            'clientId' => 'GOOGLE_API_CLIENT_ID',
            'secret' => 'GOOGLE_API_SECRET'
            'pageId' => 'GOOGLE_PLUS_PAGE_ID',
            'profileId' => 'GOOGLE_PLUS_PROFILE_ID',
        ],

        // the global settings for the google analytic plugin widget
        'googleAnalytics' => [
            'id' => 'TRACKING_ID',
            'domain' => 'TRACKING_DOMAIN',
        ],
        
        // the global settings for the twitter plugins widget
        'twitter' => [
            'screenName' => 'TWITTER_SCREEN_NAME'
        ],
    ],
    // your other modules
]
```

## What's new

I added [Google's SDK](https://github.com/google/google-api-php-client), customized this extension and ```namespace``` in ```Google SDK Source```, so you can use ```Google API``` like [Facebook API](http://demos.krajee.com/social#facebook-api)

```php
$social = Yii::$app->getModule('social');
// Get the google PHP SDK API
$ggApi  = $social->getGoogleApi();

// Output the api object
var_dump($ggApi);
```

## How to update

- Run ```composer update``` in ```sdk/google``` to update Google SDK
- Run ```conposer update``` in ```sdk/facebook``` to update Facebook SDK
- Pay attention to [Krajee](http://demos.krajee.com/social) to update the social widget's source
