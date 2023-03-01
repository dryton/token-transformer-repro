# Minimal repro of token issue

## Getting started

Run `npm i` to install the `token-transformer` package.

Run `npm run build-dark`.

Look at the output in `tokens-transformed/tokens-dark.json`.

## Expectation

The expectation here is that the colour `#00a2ba` is darkened by 30% to produce the colour `#007182` for the button press background colour.

## Actual result

The colour we receive is `#004f5b`, it appears that the colour modification happens more than once, and we end up with a colour much darker than expected.

We tested out the colour modification code directly, and it behaves as expected, so it appears that the issue is in how the tokens are processed during transformation.

To see how other tokens can interact with this, open up `tokens/core.json` and change the value `rgba($core.color.neutral.white, 0.1)` to `rgba(255, 255, 255, 0.1)` and rerun the `npm run build-dark` command.

Now you'll see that the colour value is as expected: `#007182`.


