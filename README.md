# itaym.github.io

Source for [itaym.github.io](https://itaym.github.io) - a landing page for my small React/TypeScript packages, each with a live, embedded playground.

Built with [Astro](https://astro.build). The playgrounds aren't built here - CI checks out each package's own repo, builds its `playground/` with Vite, and copies the static output into `public/playgrounds/<package>/` before the Astro build runs. See `.github/workflows/deploy.yml`.

```bash
npm install
npm run dev       # http://localhost:4321 - playgrounds are empty until you build them locally, see below
npm run build
npm run preview
```

To see playgrounds locally, build each one yourself and drop the output where the workflow expects it, e.g.:

```bash
cd ../react-single-instance/playground
npx vite build --base ./ --outDir ../../itaym.github.io/public/playgrounds/react-single-instance
```
