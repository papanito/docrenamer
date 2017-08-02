#Abstract
This script is intended to be used as nautilus-script and shall help to rename files to a specifc naming schema

#Basic Idea
There is a config file 'variables.cfg' which defines the patterns and values for the tags.
a pattern looks like this and is stored in the array 'main'
```{issuer}_{date}_Invoice.{invoiceid}```

a tag looks like {something}. First the scripts checks if there is an array in variables.cfg which corresponds to the name of the tag. If yes, it presents the user with a list of the values to choose from, otherwise the script presents a dialog to provide a free text value. Some tags are handled specially
{main} contains a list of all patterns
{date} provides a date dialog to select from