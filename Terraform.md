# Terraform

## Notes

* All environment variables that start with 'TF_VAR_variable_name' will be imported into terraform.
  * This makes something like direnv + 1pass a viable way to share sensitive variables.
* It's best to find and utilize as many safety mechanisms as possible when working with infrastructure as code. 
  * This could mean pushing some work to unit tested bash scripts.

## Modules

* Just like modules in any language, these are made to cut down on code repetition.
* Any set of files in a folder is considered a module.
* Input vars act like an API for modules.
  * they control how the code defined in the module will be named/interact in different environments.
  * these can also extend to size of provisioned items (small for staging, larger for production)
  * All of these input vars are placed in the normal vars.tf files in each module.
* Output variables or 'outputs.tf' are completely legit in Modules as well.
  * Names of outputs follow: ${module.module_name.output_name}
  * Module name is often the path to the output file, eg: 'webserver-cluster/data/etc'
* File paths are a bit weird with modules, here be dragons
* Inline blocks or nested configs should be moved into their own resource declration.
  * When working with a module/modules this is best practice.
