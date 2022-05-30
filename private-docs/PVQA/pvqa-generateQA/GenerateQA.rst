GenerateQA
++++++++++++++++++++++++++++++++

.. contents:: **Table of Contents**

In this project, we implement three modules to provide PVQA dataset:

1. Pinterest Image Downloader
2. Question Generator
3. Full-sentence Answer Generator

The repository for this project is currently private.

Pinterest Batch Downloader
===================================
Batch download images/videos from a Pinterest user profile/board/section/pin. 

This is an extension to https://github.com/limkokhole/pinterest-downloader to batch download images/videos from multiple links and supports usage of Persian letters in urls.

Getting started
------------------
Install the requirements:

``python3 -m pip install -r requirements.txt``

Usage
-------------

The links can be provided as positional arguments when running the pinterest-batch-downloader.py file, 
or written in a text file on each line (with option -file or -\-file). 

Other options will be applied to all of the links given.

.. code-block:: console

    $ python3 pinterest-batch-downloader.py --help
    usage: pinterest-batch-downloader.py [-h] [-file FILE] [-d DIR] [-j THREAD_MAX] [-c CUT] [-bt] [-lt] [-f] [-rs] [-ua]
                                    [-es] [-io] [-vo] [-ps HTTPS_PROXY] [-p HTTP_PROXY]
                                    [path ...]

    Download ALL board/section from 🅿️interest by username, username/boardname, username/boardname/section or link.
    Support image and video. Filename compose of PinId_Title_Description_Date.Ext. PinId always there while the rest is
    optional. If filename too long will endswith ... and you can check details in log-pinterest-downloader.log file.

    positional arguments:
    path                  Pinterest username, or username/boardname, or username/boardname/section, or relevant link(
                        /pin/ may include created time ).can be multiple.

    options:
    -h, --help            show this help message and exit
    -file FILE, --file FILE
                        Path to a text file that has the pinterest profile/board/section links on each line.
    -d DIR, --dir DIR     Specify folder path/name to store. Default is "images".
    -j THREAD_MAX, --job THREAD_MAX
                        Specify maximum threads when downloading images. Default is number of processors on the
                        machine, multiplied by 5.
    -c CUT, --cut CUT     Specify maximum length of "_TITLE_DESCRIPTION_DATE"(exclude ...) in filename.
    -bt, --board-timestamp
                        Suffix board directory name with unique timestamp.
    -lt, --log-timestamp  Suffix log-pinterest-downloader.log filename with unique timestamp. Default filename is log-
                        pinterest-downloader.log. Note: Pin id without Title/Description/Link/Metadata/Created_at will
                        not write to log.
    -f, --force           Force re-download even if image already exist. Normally used with -rs
    -rs, --re-scrape      Default is only fetch new images since latest(highest) Pin ID local image to speed up update
                        process. This option disable that behavior and re-scrape all, use it when you feel missing
                        images somewhere or incomplete download. This issue is because Pinterest only lists reordered
                        as you see in the webpage which possible newer images reorder below local highest Pin ID image
                        and missed unless fetch all pages.
    -ua, --update-all     Update all folders in current directory recursively based on theirs urls-pinterest-
                        downloader.urls. New section will not download. New board may download if previously download
                        by username. Options other than -c, -j, -rs, -io/vo, -ps/p will ignore. -c must same if
                        provided previously or else filename not same will re-download. Not recommend to use -c at
                        all.
    -es, --exclude-section
                        Exclude sections if download from username or board.
    -io, --image-only     Download image only. Assumed -rs
    -vo, --video-only     Download video only. Assumed -rs
    -ps HTTPS_PROXY, --https-proxy HTTPS_PROXY
                        Set proxy for https.
    -p HTTP_PROXY, --http-proxy HTTP_PROXY
                        Set proxy for http.

Check the `pinterest-downloader <https://github.com/limkokhole/pinterest-downloader>`_'s documentation for more info.

.. caution::
    Downloading files without the cut option (-c or -\-cut) may make filenames too long which in turn may cause problems when moving/copying the file to another directory. It's advised to specify a maximum length for the filenames.

Example Usage
-------------

.. code-block:: console

    $ python3 pinterest-batch-downloader.py # Prompt for insert path. Note: Only support python 3, not python 2
    $ python3 pinterest-batch-downloader.py -file mylinks.txt
    $ python3 pinterest-batch-downloader.py -file mylinks.txt https://www.pinterest.com/antonellomiglio/computer/ #Can use both the positional arguments and text file to pass the url paths.
    $ python3 pinterest-batch-downloader.py https://www.pinterest.com/antonellomiglio/computer/ https://www.pinterest.com/Foodrecipessmith/food-recipes/
    $ python3 pinterest-batch-downloader.py https://www.pinterest.com/antonellomiglio/computer/ -d comp
    $ python3 pinterest-batch-downloader.py -d comp https://www.pinterest.com/antonellomiglio/computer/ # or path in last
    $ python3 pinterest-batch-downloader.py https://www.pinterest.com/antonellomiglio/computer/ -bt -lt -d comp -f -rs # various options
    $ python3 pinterest-batch-downloader.py https://www.pinterest.com/antonellomiglio/computer/ -c 40 # Default already good enough
    $ python3 pinterest-batch-downloader.py https://www.pinterest.com/antonellomiglio/computer/ -j 666 # Default already fast enough
    $ python3 pinterest-batch-downloader.py https://www.pinterest.com/Foodrecipessmith/food-recipes/ -ps "socks4://123.123.123.123:12345" -p "socks4://123.123.123.123:12345" # set proxies

