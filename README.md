# social-media-sharer
_A javascript framework to share url to social media sites._

_Star this project on GitHub https://github.com/rsshrestha23/social-media-sharer  _

## Supported Javascript Frameworks:

- React JS
- Next Js
- Vue JS
- Angular JS

## Features

- share url to facebook
- share url to reddit
- share url to Whatsapp
- share url to twitter
- share url to linkedin
- copy url to clipboard
- Clean String

It is a lightweight javascript framework, which makes it very easy and simple to share URL to various social media sites.
social-media-sharer is created by shrestharojil.com.np

## Here is how to get started with social-media-sharer.

## Installation

Install using NPM

```sh
npm i social-media-sharer
```

Install using yarn

```sh
yarn add social-media-sharer
```

## Example 1 with React.js

```sh
import React from "react";
import { SocialMediaSharer } from "./SocialMediaSharer";

function App() {
  const sharer = new SocialMediaSharer();
  sharer.url = ""; //your url
  sharer.title = ""; //title for reddit, this is optional
  sharer.text = ""; // description for twitter, not more than a hundred characters, optional.
  sharer.hashtags = []; // a list of hashtags for twitter,also optional

  return (
    <div>
      {/* call the share method, passing the platform name as a parameter to share. */}
      <button onClick={() => sharer.share("Facebook")}>share on facebook</button>
      <button onClick={() => sharer.share("tWitter")}>share on twitter</button>
      <button onClick={() => sharer.share("WHATSAPP")}>share on Whatsapp</button>
      {/* // Or directly call the platform as a method */}
      <button onClick={() => sharer.linkedin()}>share on linkedin</button>
      <button onClick={() => sharer.reddit()}>share on reddit</button>
      <button onClick={() => sharer.copy()}>copy Link</button>
    </div>
  );
}
export default App;

```
# Note:
The parameter for the share method is case insensitive, as long as it is a valid name, the function will get executed.
the valid parameters are:
facebook, twitter, reddit, linkedin, whatsapp, copy.
## Example 2 with React.js

```sh
import React from "react";
// you can directly import these methods and use it without the SocialMediaSharer class object
import {
  facebook,
  twitter,
  reddit,
  linkedin,
  copy,
  whatsapp,
} from "./SocialMediaSharer";

function App() {
  return (
    <div>
      <button onClick={() => facebook({ url: "" })}>
        share on facebook
      </button>
      <button
        onClick={() =>
          twitter({
            url: "",
            text: "",
            hashtags: [""],
          })
        }
      >
        share on twitter
      </button>
      {/* if no url is provided, it will use the current page url. */}
      <button onClick={() => whatsapp()}>share on Whatsapp</button>
      <button onClick={() => reddit({ title: "" })}>
        share on reddit
      </button>
      <button onClick={() => copy()}>copy Link</button>
    </div>
  );
}
export default App;

```

# Note:

By default social-media-sharer   pop up a new window while sharing url, to use the parent window, you can change the target like this;

```sh
const sh = new SocialMediaSharer()
sh.target = "_parent" //by default the target is _blank
```

When no url is defined, social-media-sharer   uses the current url of the page.

You can also clean a string, before sharing it to social media site using the cleanString function. 

# Example:
```
import React from 'react'
import { cleanString } from "SocialMediaSharer";

function App(){
    const uncleanString = "The 'Quick'? Brown Fox Jump, Over The Lazy Dog;"
    const clean = cleanString(uncleanString) 
    //will return "the-quick-brown-fox-jump-over-the-lazt-dog"
    return (
    <div>
        <...../>
    </div>
    )
}
export default App;
```
