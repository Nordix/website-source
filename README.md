# website-source

Website source files for Nordix Foundation

## Set up

This site is built using [Hugo](https://gohugo.io), a static site
generator. On Ubuntu, you can install Hugo with:

```
$ sudo snap install hugo
```

For other operating systems, see the general [install
guide](https://gohugo.io/getting-started/installing).


## Test build

To preview your changes to the website locally on your laptop, you can
spin up a small local webserver with the command:

```
$ hugo server
```

The output from the command includes the URL to preview the test site
in your browser (the port will change randomly):

```
Web Server is available at http://localhost:1313/
```


## Deployment

When you're satisfied with the changes, generate the final static
website with the command:

```
$ hugo
```

Then copy the static generated files for the website from the
`public/` directory into the `nordix.github.io` repo. For example, if
you've cloned both `website-source` and `nordix.github.io` into the
same directory on your laptop, run:

```
$ cp -r public/* ../nordix.github.io/.
```

Commit your changes to both `website-source` and `nordix.github.io`, and
they'll be live on the site within a minute or two.
