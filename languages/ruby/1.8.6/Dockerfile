FROM jolicode/rbenv

# Install older openssl
RUN cd $HOME && wget http://www.openssl.org/source/openssl-0.9.8zb.tar.gz
RUN cd $HOME && tar ixzf openssl-0.9.8zb.tar.gz
RUN cd $HOME/openssl-0.9.8zb && ./config && make

RUN CFLAGS="-O2 -fno-tree-dce -fno-optimize-sibling-calls" RUBY_CONFIGURE_OPTS="--with-openssl-dir=$HOME/openssl-0.9.8zb" MAKEOPTS="" rbenv install 1.8.6-p383 && rbenv global 1.8.6-p383

# Install Bundler for each version of ruby
RUN echo 'gem: --no-rdoc --no-ri' >> /$HOME/.gemrc
