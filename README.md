# Sierra Example

A small example project built with the [Sierra Method](https://github.com/modelware/sierra-method), which it installs as the package `@modelware/sierra-method`. It models a simple device: two stakeholders with their concerns, a controller entity, and a state machine for its operating modes.

## Setup

1. Make sure the Sierra package is available in your local registry: start the registry from [`verdaccio`](https://github.com/modelware/verdaccio) and publish Sierra to it, as described in their READMEs.
2. Install the method into this repository:
   ```bash
   oml install -r http://localhost:4873
   ```
   It is installed into `deps/@modelware/sierra-method/`.

## Use

Open this repository in OML Code. The model's Sierra imports resolve to the installed package, and the notebooks in `src/md` (`Stakeholders.md`, `StateMachine.md`) use Sierra's templates.

From the command line (requires signing in to OML):

```bash
oml start
oml lint
oml codegen -c conops
oml codegen -c device
oml stop
```

The two generators come with the Sierra package: `conops` writes `build/docs/ConOps.md`, and `device` writes the state machine simulator `build/docs/Device.js`.

## Upgrading Sierra

A plain `oml install` keeps the installed version. To move to a newer one, name it:

```bash
oml install @modelware/sierra-method@^0.1.1 -r http://localhost:4873
```
