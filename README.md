# HTTP Status
Check your website http status codes in your Github Actions.

## Usage

Create your Github Workflow configuration in `.github/workflows/http_status.yml` or similar.  
Example: [http_status.yml](.github/workflows/http_status.yml)

```yml
name: Workflow for checking http status codes

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    # ... uses ....
    - name: Check http status code of production site
      uses: lakuapik/gh-actions-http-status@v1
      with:
        sites: '["http://github.com", "https://education.github.com"]'
        expected: '[301, 200]'
    # ... uses ....
```

## Inputs

The following configuration options are available:

* `sites` List website urls in JSON (eg: ["http://github.com", "https://education.github.com"])
* `expected` List expected HTTP status codes in JSON (eg: [301, 200])

*note*: please make sure the JSON are valid.

## Output
* `status_result`: The final result string.