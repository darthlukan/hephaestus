all:

install: install-program install-config

install-program:
	# Install to sbin since script is only usable by root
	install -D -m 755 hephaestus $(DESTDIR)/usr/sbin/hephaestus
	install -D -m 755 hephaestus_config $(DESTDIR)/usr/sbin/hephaestus_config
	install -D -m 755 hephaestus_root $(DESTDIR)/usr/sbin/hephaestus_root
	install -D -m 755 hephaestus_cleanup $(DESTDIR)/usr/sbin/hephaestus_cleanup

install-config:
	install -d -m 755 $(DESTDIR)/usr/share/hephaestus/
	cp -r ../share/hephaestus/* $(DESTDIR)/usr/share/hephaestus/

