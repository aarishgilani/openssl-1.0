The file is copied from felixbuenemann/openssl-1.0.2u-darwin-arm64.patch. The patch backlinks to openssl@1.1 and creats a work around to for the package to be compiled on Mac's flavour of CLang.
I had to install openssl@1.0 to be able to install older 2.3.x versions of Ruby.

Flowing are the steps to install Ruby 2.3.1 on Silicon Mac
- Download the openssl@1.0 formulae
- Install it using: brew install ~/Downloads/openssl@1.0.rb
- Once the installation finishes install Ruby using using rvm, I am using rvm after banging my head with rbenv and running into issues with gems but nevertheless rbenv works fine as well.
- `CPPFLAGS=-DUSE_FFI_CLOSURE_ALLOC rvm_rubygems_version=2.7.3 rvm reinstall ruby-2.3.1 --with-openssl-dir=/usr/local/Cellar/openssl@1.0/1.0.2u --with-openssl-lib=/usr/local/Cellar/openssl@1.0/1.0.2u/lib --with-openssl-include=/usr/local/Cellar/openssl@1.0/1.0.2u/include`
- Once the installation finishes, run rvm list and there you have it. It however show [broken] next to the version but it still worked fine for me.

  Good Luck!
