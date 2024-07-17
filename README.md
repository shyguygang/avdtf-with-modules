# ✨ Azure Terraform with Modules ✨

Prerequisites*Prequisites* - 
1. Familiarity with Terraform and modules.
2. Terraform working in your Azure environment.
3. Subscription to deploy resources.

I completed some TF code that should make lives easier.  It builds all the basics necessary for an AVD environment but it could really be used to build the basics of any Azure environment.  

It's modularized, so the root main.tf file is used to provide different variables if needed, but there's a default provided for almost everything.

Find the public repo here: https://github.com/chad-neal/avdtf-with-modules.
-----

In the root main.tf you'll find variable declarations in module blocks.

These link to the same variables declared in each modules' variables.tf.  

Specify them in the root to change what the defaults are set to.  

Or don't, if you're happy with what I've done.  

Comment out, or delete, the module blocks that you don't need/want to use.  
--------

"Terraform apply" is looking at the root main.tf, then reading each of the child modules' configurations to decide which resources to build.

Anywhere you find a declaration like module.rg.rg_name, for example, it links to the outputs.tf file stored with the module.  

In this example, in ./Modules/RG/outputs.tf, there's an object named "rg_name".  

The value of this object is coming right from the main.tf of ./modules/rg where I specify the configuration for the resource.  

Keep in mind that you can concatenate names, use wildcards, and all kinds of other things in outputs.tf to meet your needs.
