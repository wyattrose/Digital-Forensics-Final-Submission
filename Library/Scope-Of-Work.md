<!-- @Author: Dani + Wyatt -->
# Scope

This repository is for the rewrite from bash to Jython. Shouldn't take that long (depending on how much of this Mocha Frappe I can ingest).

Speaking of ingest, we're going to write out some Jython Modules that interface with Autopsy, starting with a File Ingest module.

Going to need some packages that are defined in the Autopsy documentation, we'll grab those and get it all configured before starting conversion development. - Wyatt

Extracted image files. we'll start with the first one for configuration.

Starting regular procedure for digital forensics. We're working with Powershell for this one since we didn't cover those cmdlet counterparts in class.

> [Powershell Cmdlet for File Hashing](https://https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7.6)

Completed initialization of the environment. Normally this would be enough however I need to write out some modules now. We're going to configure the development environment next.

We're keeping this repository separate from the environment modules for my own security. We'll expose the folders once they've been cleaned afterwards. - Wyatt

We're going to start with writing a script that raises flags based on file-size. This is similar to the one that we wrote in bash, however this is going to be a module written in jython. This will probably take the longest since we're still getting used to the development workflow (also appreciating being able to type at 183 WPM right now).

We're using some open-source modules to keep this as simple as possible on myself for this first script. You can find them [at this site](https://https://github.com/sleuthkit/autopsy/tree/autopsy-4.12.0/pythonExamples)

We're going to import the sample module into Autopsy to see how it works. Then we'll start performing rewrites (on a bit of time crunch right now). We're asking for an extension since this might take longer than expected.

This is a link to [The Sleuth Kit Java Bindings (JNI)](https://www.sleuthkit.org/sleuthkit/docs/jni-docs/4.6.0/classorg_1_1sleuthkit_1_1datamodel_1_1_abstract_file.html) since we're using this as a reference.

Successfully imported a module into autopsy and it returned a successful file-ingest operation. *Now the hard part*. We need to write conversions from the bash logic over to Jython. A quote from the docs actually makes development quite a bit easier:

> Whenever you have syntax errors or other errors in your script, you will get some form of dialog from Autopsy when you try to run ingest modules. If that happens, fix the problem and run ingest modules again. You don't need to restart Autopsy each time!

Going to start with the original zero timestamp module. The bash script originally checked for files that have a round file creation times. We're going to rewrite this logic in the "Process" section of the module.

We're not entirely sure how to define the scope of this project. It could be a single module with lots of logic inside, or multiple modules with individual logic for each script. Going to go with delegating to a new module for the time being.

<!-- Yup -->