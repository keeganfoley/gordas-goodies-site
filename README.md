# Gorda’s Goodies

A static HTML, CSS, and JavaScript website for a local Peruvian bakery in Springfield, Virginia.

## Preview locally

From this directory, run:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open http://localhost:8000. There is no frontend build or runtime dependency.

## Pages and ordering

- `index.html`: storefront, signature alfajores, gifts, and bakery story.
- `menu.html`: confirmed products, prices, and ordering steps.
- `about.html`: founder and business story.
- `events.html`: custom orders and celebrations.
- `gallery.html`: photo gallery with keyboard-accessible modal navigation.
- `order.html`: order form, contact, pickup, and payment information.

Order and custom-request CTAs link directly to the owner’s Google Form:
https://docs.google.com/forms/d/e/1FAIpQLSe71TklJERga9to8uqNFnMsvWOhWWvNy2QTFtBiO7dcWoFxpQ/viewform

Customers submit an order request; the owner confirms availability, the total, and pickup details before payment via Venmo or Zelle. Contact links remain available for questions. There is no on-site cart or payment processing. The order information page remains available from every footer. When changing the form URL, update all six HTML pages.

## Images

The site uses the existing logo and newly generated campaign photography. Responsive WebP files, lazy loading below the hero, and explicit image dimensions keep page loads light and reduce layout shifts. The Fraunces display font is self-hosted with its OFL license; no third-party font request is made. Generated photography uses its finished colors without extra filters.

To rebuild image assets from originals:

```sh
npm ci
npm run build-images
```

Shared baseline styling is in `css/style.css`; the bold storefront design and photo treatment are in `css/bold.css`; navigation and gallery behavior are in `js/main.js`. The static header and footer are shared by convention: update all six pages when changing their content.

## Design references

The storefront refresh draws on Etsy’s product and gift browsing, and the bakery-focused presentation of Levain and Last Crumb, while retaining Gorda’s original crimson logo, cream palette, real products, and personal ordering model.

- https://www.etsy.com/market/alfajores
- https://levainbakery.com/
- https://lastcrumb.com/


## Campaign photography

All displayed food photos now use the new Higgsfield campaign collection, including
the story section, kitchen details, and gallery. Original photos remain archived
on disk but are not referenced by the website. The gallery is styled inspiration,
not a record of actual customer events. Generation provenance is saved alongside
the source images in `assets/generated`.

Run `npm run build-generated-images` to export 400, 700, 1200, and 1600 pixel
WebP variants without enlarging source images.

The additional assortment set in `assets/generated/assortment` includes a
mixed platter, chocolate alfajores, and flowers/stars. These are used on the
homepage, menu flavor guide, and events intro. The image export script also
processes these nested source folders.

## Logo exports

`npm run build-logo` trims only the empty margins of the original 6251×4167
artwork and exports the unchanged logo at 320, 640, and 1280 pixels wide.
`images/logo-master.png` retains the cropped 2551×2693 source resolution.
Header and footer use responsive PNG sources without CSS enlargement.

## Packaging concepts

The homepage gifting feature and Events intro use `packaging/box-1` and
`packaging/box-3`, respectively: AI-styled cream gift boxes carrying the existing
brand artwork. They are labeled as concepts, with real packaging options to be
confirmed when ordering. The unused open-lid alternate altered the logo and is
not displayed on the website. Sources and generation notes are under
`assets/generated/packaging`.

## Shareable redesign preview

The `redesign-preview` branch on `keeganfoley/gordas-goodies-site` contains the
redesign. GitHub Pages serves that branch from the repository root at
https://keeganfoley.github.io/gordas-goodies-site/ . The upstream company's
`main` branch and existing website are unchanged.
