# Giphy Selector Custom Element for Kentico Kontent

This is a [custom element](https://docs.kontent.ai/tutorials/develop-apps/integrate/integrating-your-own-content-editing-features) for [Kentico Kontent](https://kontent.ai) that allows you to search Giphy and select one.

![Screenshot of custom element](GiphySelector.gif)

## Setup

1. Get a [Giphy API Key](https://developers.giphy.com/)
1. Deploy the code to a secure public host
    * See [deploying section](#Deploying) for a really quick option
1. Follow the instructions in the [Kentico Kontent documentation](https://docs.kontent.ai/tutorials/develop-apps/integrate/integrating-your-own-content-editing-features#a-3--displaying-a-custom-element-in-kentico-kontent) to add the element to a content model.
    * The `Hosted code URL` is where you deployed to in step 1
    * Pass the required parameters as directed in the [JSON Parameters configuration](#json-parameters) section of this readme.

## Deploying

Netlify has made this easy. If you click the deploy button below, it will guide you through the process of deploying it to Netlify and leave you with a copy of the repository in your GitHub account as well.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/Kentico/kontent-custom-element-giphy-selector)

## JSON Parameters

The `apiKey` property is required. This is your [Giphy API key](https://developers.giphy.com/).

All other keys are optional. The optional parameters are:

* limit - number
  * The number of image results to return in the response. The actual number delivered may be less than requested.
* offset - number
  * The zero-based offset that indicates the number of image results to skip before returning results.
* rating - string
  * Filter result by rating, possible options are : Y, G, PG, PG-13, R
* lang
  * Specify [default language](https://developers.giphy.com/docs/optional-settings/#language-support) for regional content; use a 2-letter ISO 639-1 language code.

```Json
{
    "apikey": "[YOUR API KEY]",
    "limit": 10,
    "offset": 0,
    "rating": "G",
    "lang": "en"
}
```

## Saved Value

The value is saved as a string representing the URL of the gif. The URL is pulled from the "fixed height" portion of the Giphy API response.

## Contributors

Originally contributed by [@maartenvdh](https://github.com/maartenvdh/)
