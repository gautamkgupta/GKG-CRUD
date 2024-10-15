PHP
The PHP Interpreter
PHP is a popular general-purpose scripting language that is especially suited to web development. Fast, flexible and pragmatic, PHP powers everything from your blog to the most popular websites in the world. PHP is distributed under the PHP License v3.01.

Push Fuzzing Status

Documentation
The PHP manual is available at php.net/docs.

Installation
Prebuilt packages and binaries
Prebuilt packages and binaries can be used to get up and running fast with PHP.

For Windows, the PHP binaries can be obtained from windows.php.net. After extracting the archive the *.exe files are ready to use.

For other systems, see the installation chapter.

Building PHP source code
For Windows, see Build your own PHP on Windows.

For a minimal PHP build from Git, you will need autoconf, bison, and re2c. For a default build, you will additionally need libxml2 and libsqlite3.

On Ubuntu, you can install these using:

sudo apt install -y pkg-config build-essential autoconf bison re2c \
                    libxml2-dev libsqlite3-dev
On Fedora, you can install these using:

sudo dnf install re2c bison autoconf make libtool ccache libxml2-devel sqlite-devel
Generate configure:

./buildconf
Configure your build. --enable-debug is recommended for development, see ./configure --help for a full list of options.

# For development
./configure --enable-debug
# For production
./configure
Build PHP. To speed up the build, specify the maximum number of jobs using -j:

make -j4
The number of jobs should usually match the number of available cores, which can be determined using nproc.

Testing PHP source code
PHP ships with an extensive test suite, the command make test is used after successful compilation of the sources to run this test suite.

It is possible to run tests using multiple cores by setting -jN in TEST_PHP_ARGS:

make TEST_PHP_ARGS=-j4 test
Shall run make test with a maximum of 4 concurrent jobs: Generally the maximum number of jobs should not exceed the number of cores available.

The qa.php.net site provides more detailed info about testing and quality assurance.

Installing PHP built from source
After a successful build (and test), PHP may be installed with:

make install
Depending on your permissions and prefix, make install may need super user permissions.

PHP extensions
Extensions provide additional functionality on top of PHP. PHP consists of many essential bundled extensions. Additional extensions can be found in the PHP Extension Community Library - PECL.

Contributing
The PHP source code is located in the Git repository at github.com/php/php-src. Contributions are most welcome by forking the repository and sending a pull request.

Discussions are done on GitHub, but depending on the topic can also be relayed to the official PHP developer mailing list internals@lists.php.net.

New features require an RFC and must be accepted by the developers. See Request for comments - RFC and Voting on PHP features for more information on the process.

Bug fixes don't require an RFC. If the bug has a GitHub issue, reference it in the commit message using GH-NNNNNN. Use #NNNNNN for tickets in the old bugs.php.net bug tracker.

Fix GH-7815: php_uname doesn't recognise latest Windows versions
Fix #55371: get_magic_quotes_gpc() throws deprecation warning
See Git workflow for details on how pull requests are merged.

Guidelines for contributors
See further documents in the repository for more information on how to contribute:

Contributing to PHP
PHP coding standards
Internal documentation
Mailing list rules
PHP release process
Credits
For the list of people who've put work into PHP, please see the PHP credits page.