# Templated SDL Files for Automated Deployments

Easily update Akash SDL files, with dynamic values to drive automated deployments.

## Inputs

### `TEMPLATE_PATH`

(default: `deploy.tmpl`) template file to target for transform

### `OUT_PATH`

(default: `deploy.yaml`) target file to output transformed file

## Example usage

In the github action runner, pass the templated values to the step as `env` variables. Additionally you can set `TEMPLATE_PATH` and `OUT_PATH`

```yaml
- name: Akash Update SDL
    uses: ovrclk/akash-ghaction-templated-sdl@v1
    env:
        MY_KEY: MY_VALUE
```

Create a file `deploy.tmpl` as an example. Use the template placeholder, where dynamic values are required. `{{ .Env.MY_KEY }}`

```yaml
version: "2.0"

services:
  web:
    image: myimage:{{ .Env.MY_KEY }}
```
