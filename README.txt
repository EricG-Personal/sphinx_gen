This project relates to a question on a behavior difference between sphinx 1.6.3 and 1.6.6

When the command sphinx-apidoc -o . a_package is executed, both versions will create:

a_package.rst
a_package.sub_package.rst
modules.rst

However, the contents of a_package.rst are different.

In v1.6.3, the first few lines of the document look like:

    a\_package package
    ==================

    Subpackages
    -----------

    .. toctree::

        a_package.sub_package


The item to note is that it includes a Subpackages section with a_package.sub_package in the toctree.

v1.6.6 does not generate these lines with the same command. So, when making the html version of the docs, a warning which says:

    sphinx_gen/a_package.sub_package.rst: WARNING: document isn't included in any toctree
    
is generated.

The question is whether or not this is a bug in 1.6.6 and what is the best way to obtain the same behavior that existed in 1.6.3.
