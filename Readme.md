# Heritrix crawllog analysis

## Introduction

Large harvests are a hard task for QA without proper tools. These scripts will help you with semi-manual quality assurance by grouping and filtering data and calculating metrics.

## Duplicate Checking

Checks a crawl.log for duplicate files determined by hash value. This is useful if your harvest is unexpectedly big as a website might might deliver the same content under different URLs (there are for example websites delivering wrong pages instead of 404 repsonse codes).

You can filter for URLs corresponding to certain response codes. If you don't, everything is analyzed.

Usage:

    $ python check_for_duplicates.py --help
    usage: check-for-duplicates.py [-h] [-o OUT] [-c CODE] crawl_log

    positional arguments:
     crawl_log

    optional arguments:
     -h, --help            show this help message and exit
     -o OUT, --out OUT
     -c CODE, --code CODE  HTTP response code to filter before checking for
                           duplicates.

## Compare Logfiles

You ran two crawls with different settings and want to know how the crawl has changed? `look_for_missing_urls.py` compares two `crawl.log` files and generates a report which URLs are missing in the *second* one

Usage:

    $ python look_for_missing_urls.py --help
    usage: look-for-missing-urls.py [-h] [-o OUT] reference compare

    positional arguments:
     reference
     compare

    optional arguments:
     -h, --help         show this help message and exit
     -o OUT, --out OUT

## Sort by Response Code

The script `sort_by_respose_code.py` sorts all URLs by response code.

Usage:

    $ python sort_by_respose_code.py --help
    usage: sort_by_respose_code.py [-h] [-o OUT] crawl_log

    positional arguments:
      crawl_log

    optional arguments:
      -h, --help         show this help message and exit
      -o OUT, --out OUT