# Kirbyup HMR Playground

### Instructions

```sh
# Clone
git clone --recurse-submodules https://github.com/jonaskuske/kirbyup-hmr-playground hmr && cd $_

# Build kirbyup
pnpm --prefix kirbyup install
pnpm --prefix kirbyup build

# Link and configure demo plugin
cd site/plugins/demo
pnpm link ../../../kirbyup
sed -i "s/\/\/ plugin magic happens here/'sections' => ['demo' => []]/" index.php

# Run kirbyup dev server
pnpm kirbyup serve src/index.js
```

...then in another terminal/tab, start kirby with `pnpm start` and visit [`http://localhost:8080/panel`](http://localhost:8080/panel).

Now you can edit `site/plugins/demo/src/components/DemoSection.vue` and see the changes reflected in real-time!
