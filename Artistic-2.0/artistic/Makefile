# The Artistic License Japanese Translation
# Makefile
# created on 2001/5/30
# by Oohara Yuuma
# Copyright (C) 2001 Oohara Yuuma

# where you want to install this package
PREFIX=/usr/local
# where you want to install man pages
PREFIXMAN=/usr/local/man
# the command to create directories for installation
INSTALLDIR=install -d -m 755
# the command to install documents
INSTALLDATA=install -m 644

all: Artistic.7.gz ja/Artistic.7.gz

Artistic.7.gz: Artistic.7
	cp Artistic.7 Artistic.7.bak
	gzip -9f Artistic.7
	mv Artistic.7.bak Artistic.7
	touch Artistic.7.gz

ja/Artistic.7.gz: ja/Artistic.7
	cp ja/Artistic.7 ja/Artistic.7.bak
	gzip -9f ja/Artistic.7
	mv ja/Artistic.7.bak ja/Artistic.7
	touch ja/Artistic.7.gz

.PHONY: clean

clean:
	-rm -f Artistic.7.gz ja/Artistic.7.gz

# You need nkf to do "make prepack".
prepack: changelog-sjis.txt README-sjis.txt \
  ja-sjis/Artistic-ja.html ja-sjis/Artistic-ja.txt \
  INSTALL-sjis.txt

changelog-sjis.txt: changelog.txt
	nkf -sc changelog.txt > changelog-sjis.txt

README-sjis.txt: README.txt
	nkf -sc README.txt > README-sjis.txt

ja-sjis/Artistic-ja.html: ja/Artistic-ja.html
	nkf -sc ja/Artistic-ja.html > ja-sjis/Artistic-ja.html

ja-sjis/Artistic-ja.txt: ja/Artistic-ja.txt
	nkf -sc ja/Artistic-ja.txt > ja-sjis/Artistic-ja.txt

INSTALL-sjis.txt: INSTALL.txt
	nkf -sc INSTALL.txt > INSTALL-sjis.txt 

# "make install" must be done by root
install: all
	$(INSTALLDIR) $(PREFIX)/share/doc/artistic-ja
	$(INSTALLDIR) $(PREFIX)/share/doc/artistic-ja/ja
	$(INSTALLDIR) $(PREFIX)/share/doc/artistic-ja/ja-sjis
	$(INSTALLDIR) $(PREFIXMAN)/man7
	$(INSTALLDIR) $(PREFIXMAN)/ja/man7
	$(INSTALLDATA) Artistic.7.gz $(PREFIXMAN)/man7
	$(INSTALLDATA) COPYRIGHT.txt $(PREFIX)/share/doc/artistic-ja
	$(INSTALLDATA) README-sjis.txt $(PREFIX)/share/doc/artistic-ja
	$(INSTALLDATA) README.txt $(PREFIX)/share/doc/artistic-ja
	$(INSTALLDATA) changelog-sjis.txt $(PREFIX)/share/doc/artistic-ja
	$(INSTALLDATA) changelog.txt $(PREFIX)/share/doc/artistic-ja
	$(INSTALLDATA) ja-sjis/Artistic-ja.html \
$(PREFIX)/share/doc/artistic-ja/ja-sjis
	$(INSTALLDATA) ja-sjis/Artistic-ja.txt \
$(PREFIX)/share/doc/artistic-ja/ja-sjis
	$(INSTALLDATA) ja/Artistic-ja.html \
$(PREFIX)/share/doc/artistic-ja/ja
	$(INSTALLDATA) ja/Artistic-ja.txt \
$(PREFIX)/share/doc/artistic-ja/ja
	$(INSTALLDATA) ja/Artistic.7.gz $(PREFIXMAN)/ja/man7

.PHONY: packclean

packclean:
	-rm -f changelog-sjis.txt README-sjis.txt \
  ja-sjis/Artistic-ja.html ja-sjis/Artistic-ja.txt \
  INSTALL-sjis.txt

# "make uninstall" must be done by root
.PHONY: uninstall

uninstall:
	-rm -f $(PREFIXMAN)/man7/Artistic.7.gz
	-rm -f $(PREFIXMAN)/ja/man7/Artistic.7.gz
	-rm -f $(PREFIX)/share/doc/artistic-ja/COPYRIGHT.txt
	-rm -f $(PREFIX)/share/doc/artistic-ja/README.txt
	-rm -f $(PREFIX)/share/doc/artistic-ja/README-sjis.txt
	-rm -f $(PREFIX)/share/doc/artistic-ja/changelog-sjis.txt
	-rm -f $(PREFIX)/share/doc/artistic-ja/changelog.txt
	-rm -f $(PREFIX)/share/doc/artistic-ja/ja-sjis/Artistic-ja.html
	-rm -f $(PREFIX)/share/doc/artistic-ja/ja-sjis/Artistic-ja.txt
	-rm -f $(PREFIX)/share/doc/artistic-ja/ja/Artistic-ja.html
	-rm -f $(PREFIX)/share/doc/artistic-ja/ja/Artistic-ja.txt
	-rmdir $(PREFIXMAN)/ja/man7
	-rmdir $(PREFIXMAN)/ja/
	-rmdir $(PREFIXMAN)/man7
	-rmdir $(PREFIX)/share/doc/artistic-ja/ja
	-rmdir $(PREFIX)/share/doc/artistic-ja/ja-sjis
	-rmdir $(PREFIX)/share/doc/artistic-ja
	-rmdir $(PREFIX)/share/doc
	-make clean
