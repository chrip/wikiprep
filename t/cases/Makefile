LOGS =	images.log \
	urlencode.log \
	parserfunctions.log \
	anchors.log \
	redir.log \
	categories.log \
	templates.log \
	disambig.log \
	order.log \
	citebook.log \
	gallery.log \
	unicode.log \
	anchorspace.log \
	citeweb.log \
	missinganchors.log \
	infobox.log \
	nowiki.log \
	imagemap.log \
	enwiki-20080103-pages-articles.log \
	xmlcomments.log \
	nestedtables.log \
	div.log \
	languages.log \
	barzilla.log \
	ifeq.log \
	asse.log \
	hurt.log \
	microsoft.log \
	microsoft2.log \
	window.log \
	intel.log \
	nonfreegamecover.log \
	olympics.log \
	tibet.log \
	externalurls.log \
	coord.log \
	riemann.log \
	carbon.log \
	dates.log \
	related.log \
	css.log \
	css2.log \
	whitespace.log \
	kaon2.log \
	segfault.log \
	noinclude.log \
	interwiki.log \
	tempredir.log \
	microsoft-new.log \
	interwiki-new.log \
	headings.log \
	dblredir.log \
	otheruses.log \
	geo.log \
	stub.log \
	mainarticle.log \
	magicwords.log \
	commons-theatre.log \
	apple.log \
	mac.log

OPTIONS=$(shell grep "^$<:" options | sed -e 's/^[^:]*://')

TOPDIR="../.."

all: test

test: clean $(LOGS) compare

%.log: %.xml
	perl -I$(TOPDIR)/lib $(TOPDIR)/bin/wikiprep -log debug $(OPTIONS) -f $<
	for n in `basename $< .xml`*.xml; do xmllint --noout $$n || exit 1; done
clean:
	rm -f *.anchor_text
	rm -f *.anchor_text.sorted
	rm -f *.external_anchors
	rm -f *.cat_hier
	rm -f *.hgw.xml
	rm -f *.local.xml
	rm -f *.log
	rm -f *.related_links
	rm -f *.stat.categories
	rm -f *.stat.inlinks
	rm -f *.redir.xml
	rm -f *.disambig
	rm -f *.min_local_id
	rm -f *.version
	rm -f *.gum.xml
	rm -f *.tmpl.xml
	rm -f *.redir.db *.title2id.db *.templates.db *.namespaces.db *.count.db
	rm -rf *.templates
	rm -rf *.interwiki
	rm -f *.interwiki.xml
	rm -f *.profile

compare:
	./compare

.PHONY: clean compare test all
