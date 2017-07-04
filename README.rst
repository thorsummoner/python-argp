.. code-block:: python

    #!/usr/bin/env python3

    """ Example argparser based python script.

        This docblock becomes the help page header description.
    """

    import argparse


    ARGP = argparse.ArgumentParser(
        description=__doc__,
        formatter_class=argparse.RawTextHelpFormatter,
    )
    ARGP.add_argument('--debug', action='store_true', help='Dump arguments')


    def main(argp=None):
        """ Command line entry point.
        """
        if argp is None:
            argp = ARGP.parse_args()

        print(argp.debug)


    if __name__ == '__main__':
        main()

Example help output:

::

    usage: gh-iter [-h] [--debug]

     Example argparser based python script.

        This docblock becomes the help page header description.

    optional arguments:
      -h, --help  show this help message and exit
      --debug     Dump arguments
