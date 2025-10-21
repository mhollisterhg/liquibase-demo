# idp-generic-template

Generic template for IDP projects.

If you would like to use custom templates instead of a one-size-fits-all generic template, please refer to the 
documentation at https://github.com/HGData/terraform-github-repo for more information.

A template is recommended when using Terraform to create new repos via https://github.com/HGData/ops-github. It is 
used to automatically set up branches, code owners, Dependabot configuration, etc.

## Things to customize

* `.github/dependabot.yml` to manage project dependency updates
* `.github/CODEOWNERS` if you'd like to have code owners
* `README.md`
