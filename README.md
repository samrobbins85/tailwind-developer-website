![GitHub](https://img.shields.io/github/license/samrobbins85/tailwind-developer-website?style=for-the-badge)

# Developer Portfolio

![Website Image](https://res.cloudinary.com/samrobbins/image/upload/v1599818555/Screenshot_2020-09-11_Sam_Robbins_r5wqm6.png)

## Installation

### Integrating into your site

To install this theme, first create a themes folder in your site with

```bash
mkdir themes
```

Then move into this directory with

```bash
cd themes
```

The repository can then be added either by cloning or adding as a submodule

```bash
# Cloning
git clone https://github.com/samrobbins85/tailwind-developer-website
tailwind-developer-website
# Submodule
git submodule add https://github.com/samrobbins85/tailwind-developer-website tailwind-developer-website
```

In the `config.toml` file in your site directory add

```toml
theme="tailwind-developer-website"
```

### Creating a new site

The exampleSite folder is all set up to work as a site, just copy it out of the Git repo and it will work. You need to have golang installed as it uses [hugo modules](https://gohugo.io/hugo-modules/use-modules/).

## Configuration

This is a highly configurable site, and as such, it will be unlikely that it will work with your existing site.

### `Config.toml`

`Config.toml` provides the basic structure of the site, it contains a range of sections

#### Base information

In the example site, the base information looks as follows

```toml
baseURL = "http://example.com" # The URL of your site
languageCode = "en-gb" # The language you want to display the site in
title = "Sam Robbins" # The title you want to appear in the address bar
theme = "tailwind-developer-website" # The theme, don't change this
```

#### Params

This contains the other configuration information

```toml
[params]
home = "Home" # What you want the homepage to show up as in the menu bar
# Meta data
description = "The website of Sam Robbins, 2nd Year Computer Science Student at Durham University"
author = "Sam Robbins"
```

### `homepage.yml`

This file is stored in `data/homepage.yml`. It determines the content of the homepage and contains many sections

#### social

Put all of your social links here and they will appear in the social section

```yml
social:
  twitter: ""
  linkedin: sam-robbins-gb
  github: samrobbins85
  gitlab: ""
  facebook: ""
  instagram: ""
  gmail: samrobbinsgb
```

#### portfolio

This is used to highlight specific portfolio projects you want to show

- `enable` can be used to hide this section
- `title` is the text at the top each item
- `company` to show who you did the work for
- `date` displays under the title
- `image` is the image for each item
- `description` for a short description of the project
- `link` directs to the main portfolio page
- `tools` indicates what technologies you used

```yml
portfolio:
  enable: true
  item:
    - title: DNS Comparison Website
      company: Global Cyber Alliance
      date: 2020
      image: https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1599472461/homepage_urjka3.png
      description: A website to compare the performance of major DNS providers when it comes to blocking criminal domains
      link: "/portfolio/dns-comparison-website/"
      tools:
        - https://cdn.svgporn.com/logos/nextjs.svg
        - https://cdn.svgporn.com/logos/tailwindcss-icon.svg
```

#### Achievements

This allows you to list your achievements in the following format

The colour for `background` is based on the [Tailwind CSS](https://tailwindcss.com/) colours, you can read more about them [here](https://tailwindcss.com/docs/customizing-colors)

```yml
achievements:
  enable: true
  item:
    - title: Auth0 Hackathon
      description: 3rd Place Security
      date: July 2020
      image: https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1591793268/logos/logos_auth0_ruvdmp.svg
      background: bg-orange-100
```

### `about.yml`

#### experience

- `enable` can be used to hide this section
- `logo` determines the image that shows up
- `title` is the main text
- `company` is the secondary text
- `duration` is the tertiary text
- `background` follows the same format as the Achievements section

```yml
experience:
  enable: true
  item:
    - logo: https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1597050679/icon_fjhqxr.png
      title: Student Intern
      company: Global Cyber Alliance
      duration: July 2020 - September 2020
      background: bg-blue-100
```

#### hackathons

By placing none in the URL field, the image will be rendered without any links

```yml
hackathons:
  enable: true
  item:
    - title: Hack Cambridge 2019
      description: Climate change simulator
      image: https://res.cloudinary.com/samrobbins/image/upload/f_auto,q_auto/v1591793405/stickers/Hack_Cambridge_101_ozoq5d.png
      url: none
```

#### education

This section allows you to showcase your education history, the fields are self explanatory, apart from `background` which follows the same format as the other sections that take a background property

```yml
education:
  enable: true
  item:
    - title: BSc Computer Science
      duration: 2018 - Present
      institution: Durham University
      image: https://res.cloudinary.com/samrobbins/image/upload/f_auto,q_auto/v1591793268/logos/logos_Durham_fc2sae.svg
      background: bg-purple-100
```

#### skills

These fields are self explanatory, enable can be used to hide this section

```yml
skills:
  enable: true
  item:
    - name: Next.js
      image: https://cdn.svgporn.com/logos/nextjs.svg
      url: https://nextjs.org
    - name: Tailwind CSS
```

### `porfolio.yml`

This file configures the portfolio page, allowing you to specify the filters you want to use.

```yml
filter:
  - label: Web Dev
    value: web-dev
```

### Blogs

When submitting a blog, you can supply the following fields in the front matter

```yml
title: "Making a new Website"
date: 2019-12-31T12:14:34+06:00
image: "https://d33wubrfki0l68.cloudfront.net/c38c7334cc3f23585738e40334284fddcaf03d5e/2e17c/images/hugo-logo-wide.svg"
description: "My first blog, introducing my new website"
author: "Sam Robbins"
```

### Portfolio pages

The portfolio page and blog page use the same configuration, so you can use these new fields if you want, but they are more suited to portfolio pages

```toml
categories = ["hackathon", "web-dev"]
coders = ["samrobbins85", "karina-talibzhanova"]
date = 2020-05-30T23:00:00Z
description = "A Firefox Browser Extension"
github = ["https://github.com/karina-talibzhanova/oxfordhack2020"]
image = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593352345/twoo-home_k7molq.png"
title = "Oxford Digithon"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1591793272/logos/logos_javascript_adj1dx.svg"
name = "JavaScript"
url = "https://www.ecma-international.org/memento/tc39.htm"
[[tech]]
logo = "https://res.cloudinary.com/samrobbins/image/upload/q_auto/v1593368547/firefox-ar21_cps6me.svg"
name = "Firefox WebExtensions"
url = "https://www.mozilla.org/en-GB/firefox/"
```

The [[tech]] item can be repeated as many times as you desire.
