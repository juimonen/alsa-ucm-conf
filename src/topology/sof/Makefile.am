topologydir = @TOPOLOGY_CONFIG_DIR@
topology_DATA = \
	sof-apl-pcm512x.tplg

MACHINES = \
	sof-apl-pcm512x.tplg

%.tplg : %.conf
	alsatplg -v 1 -c $< -o $@

all: ${MACHINES}

clean-local:
	rm -f *.tplg

EXTRA_DIST = $(topology_DATA)
