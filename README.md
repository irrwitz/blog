# blog

## local
To create page run
`pelican content`

To serve run
`python -m pelican.server`
in the output directory

## publish to github
```shell
pelican content -o output -s pelicanconf.py
ghp-import output
git push git@github.com:joshy/joshy.github.io.git gh-pages:master
```