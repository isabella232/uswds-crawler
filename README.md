This repository contains some tooling that can be used to quickly
obtain information about how websites use the
[U.S. Web Design Standards][uswds].

## Quick start

You'll need [Node JS][] version 7.10 or greater.

```
npm install
node cache-sites.js
```

At this point, the front page of all sites that use the Standards
will be cached in the `cache` directory. At this point you can
run queries, described below.

## Queries

### Finding bad gov banners

To find sites that are using [bad gov banners][], run:

```
node find-bad-govbanners.js
```

[bad gov banners]: https://github.com/18F/web-design-standards/issues/1738

### Finding class usage

To find statistics about the usage of particular USWDS classes, run:

```
node find-usa-class-usage.js
```

Note that this only finds USWDS classes if they are namespaced via
the default `usa-` prefix. If a website is using a custom build of
USWDS that changes this default prefix, its use of USWDS classes
won't be detected.

## Clearing and re-populating the cache

To clear your cached copies of the front pages of all Standards sites,
just delete the `cache` directory, e.g. `rm -rf cache`.

Then run `node cache-sites.js` to re-populate the cache with the latest
version of each page.

## Updating the site list

The site list is stored in the [`WHO_IS_USING_USWDS.md`][] file in
the Standards repository. To change the version of the repository
used to obtain the list, change the `uswds` dependency in `package.json`.

[uswds]: https://standards.usa.gov/
[Node JS]: https://nodejs.org/
[`WHO_IS_USING_USWDS.md`]: https://github.com/18F/web-design-standards/blob/develop/WHO_IS_USING_USWDS.md
