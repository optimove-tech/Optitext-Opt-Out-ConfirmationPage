# Optitext Opt Out Confirmation Page

## Background

This repository contains an example opt out page for use with Optimove opt out links.

Opt out links are hyperlinks that redirect to a page allowing opt out. Each opt out link contains a user specific 'slug' (e.g. abcd1234). For example:

```
https://optouttxt.net/abcd1234
```
_Example opt out link, in this case the user slug is abcd1234_

When the end user follows an opt out link, they will be redirected to a confirmation page (e.g. index.html).  The redirection will also include the user slug e.g.

```
https://optitext-opt-out.optimove.net/index.html?slug=abcd1234
```

Upon the user confirming the desire to opt out - a round trip must be made back to the lookup service including both the path slug and the query string variable `confirm=1`.  For example:

```
https://optouttxt.net/abcd1234?confirm=1
```
_Example opt out link confirmed_

This will queue backend opt out tasks and then redirect back to your confirm page with `confirm=1`. For example:

```
https://optitext-opt-out.optimove.net/index.html?confirm=1
```

When creating opt out links, you can use the default confirmation page (hosted by Optimove) at https://optitext-opt-out.optimove.net/index.html.

Alternatively you can 'self-host' a confirmation page by using the code in this repository as a basis. Self hosting allows for custom branded opt out pages e.g. with company logo etc.

## Using this page

You can access this page by cloning the repository and visiting it in your browser (using the `file://` protocol).

Test that changes to your page work by calling it either with:

```
index.html?slug=abcd1234
```

or the confirmation side

```
index.html?confirm=1
```

