## Abstract

This script is intended to be used as nautilus-script and shall help to rename files to a specific naming schema

## Background

I usually scan all my paper documents (no ocr) so I want to be able to find them easily. Therefore I rename them to a specific naming scheme (and save them in a well defined folder structure)

## Script Summary

There is a config file `variables.cfg` which defines the patterns and values for the tags.
a pattern looks like this and is stored in the array 'main'

```blank
{issuer}_{date}_Invoice.{invoiceid}
```

a tag looks like `{something}`. First the scripts checks if there is an array in variables.cfg which corresponds to the name of the tag. If yes, it presents the user with a list of the values to choose from, otherwise the script presents a dialog to provide a free text value. Some tags are handled specially

- `{main}` contains a list of all patterns
- `{date}` provides a date dialog to select from

## Troubleshooting

### Conversion fails

Conversion from `png` to `pdf` fails with

```bash
attempt to perform an operation not allowed by the security policy `PDF' @ error/constitute.c/IsCoderAuthorized/408.
```

https://bugs.archlinux.org/task/60580

> Parsing PDF was disabled[1] in /etc/ImageMagick-7/policy.xml due to its inherent insecurity. The same thing did Ubuntu and perhaps more distros will follow as this is recommendation from security researchers.
>
> You may enable it locally by removing 'PDF' from below line:
> `<policy domain="coder" rights="none" pattern="{PS,PS2,PS3,EPS,PDF,XPS}" />`
