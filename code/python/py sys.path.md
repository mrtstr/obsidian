## [[py sys.path]]
A list of strings that specifies the search path for [[py module|modules]]. 
It is initilized with the following priority
1) The directory containing the input script (or the current directory when no file is specified).
2) `PYTHONPATH`
3) installation-dependent default (by convention including a `site-packages` directory,

-   `python -m module` command line: prepend the current working directory.
-   `python script.py` command line: prepend the script’s directory.

After initialization, Python programs can modify `sys.path`. The directory containing the script being run is placed at the beginning of the search path, ahead of the standard library path


# anki

START
Basic
[[py sys.path]]
- what is it
- what is it used for
Back: 
A list of strings that specifies the search path for modules. 
It is initilized with the following priority
1) The directory containing the input script (or the current directory when no file is specified).
2) `PYTHONPATH`
3) installation-dependent default (by convention including a `site-packages` directory,

-   `python -m module` command line: prepend the current working directory.
-   `python script.py` command line: prepend the script’s directory.

After initialization, Python programs can modify `sys.path`. The directory containing the script being run is placed at the beginning of the search path, ahead of the standard library path
Tags: code python
<!--ID: 1698674406727-->
END