
	List of maintainers and how to submit driver changes

Please try to follow the guidelines below.  This will make things
easier on the maintainers.  Not all of these guidelines matter for every
trivial patch so apply some common sense.

1.	Always _test_ your changes, however small, on at least 4 or
	5 people, preferably many more.

2.	Try to release a few ALPHA test versions to the net. Announce
	them onto the kernel channel and await results. This is especially
	important for device drivers, because often that's the only way
	you will find things like the fact version 3 firmware needs
	a magic fix you didn't know about, or some clown changed the
	chips on a board and not its name.  (Don't laugh!  Look at the
	SMC etherpower for that.)

3.	Make sure your changes compile correctly in multiple
	configurations. In particular check that changes work both as a
	module and built into the kernel.

4.	When you are happy with a change make it generally available for
	testing and await feedback.

5.	Make a patch available to the relevant maintainer in the list. Use
	'diff -u' to make the patch easy to merge. Be prepared to get your
	changes sent back with seemingly silly requests about formatting
	and variable names.  These aren't as silly as they seem. One
	job the maintainers (and especially Linus) do is to keep things
	looking the same. Sometimes this means that the clever hack in
	your driver to get around a problem actually needs to become a
	generalized kernel feature ready for next time.

	PLEASE check your patch with the automated style checker
	(scripts/checkpatch.pl) to catch trival style violations.
	See Documentation/CodingStyle for guidance here.

	PLEASE CC: the maintainers and mailing lists that are generated
	by scripts/get_maintainer.pl.  The results returned by the
	script will be best if you have git installed and are making
	your changes in a branch derived from Linus' latest git tree.
	See Documentation/SubmittingPatches for details.

	PLEASE try to include any credit lines you want added with the
	patch. It avoids people being missed off by mistake and makes
	it easier to know who wants adding and who doesn't.

	PLEASE document known bugs. If it doesn't work for everything
	or does something very odd once a month document it.

	PLEASE remember that submissions must be made under the terms
	of the OSDL certificate of contribution and should include a
	Signed-off-by: line.  The current version of this "Developer's
	Certificate of Origin" (DCO) is listed in the file
	Documentation/SubmittingPatches.

6.	Make sure you have the right to send any changes you make. If you
	do changes at work you may find your employer owns the patch
	not you.

7.	When sending security related changes or reports to a maintainer
	please Cc: security@kernel.org, especially if the maintainer
	does not respond.

8.	Happy hacking.

Descriptions of section entries:

	P: Person (obsolete)
	M: Mail patches to: FullName <address@domain>
	L: Mailing list that is relevant to this area
	W: Web-page with status/info
	Q: Patchwork web based patch tracking system site
	T: SCM tree type and location.  Type is one of: git, hg, quilt, stgit, topgit.
	S: Status, one of the following:
	   Supported:	Someone is actually paid to look after this.
	   Maintained:	Someone actually looks after it.
	   Odd Fixes:	It has a maintainer but they don't have time to do
			much other than throw the odd patch in. See below..
	   Orphan:	No current maintainer [but maybe you could take the
			role as you write your new code].
	   Obsolete:	Old code. Something tagged obsolete generally means
			it has been replaced by a better system and you
			should be using that.
	F: Files and directories with wildcard patterns.
	   A trailing slash includes all files and subdirectory files.
	   F:	drivers/net/	all files in and below drivers/net
	   F:	drivers/net/*	all files in drivers/net, but not below
	   F:	*/net/*		all files in "any top level directory"/net
	   One pattern per line.  Multiple F: lines acceptable.
	X: Files and directories that are NOT maintained, same rules as F:
	   Files exclusions are tested before file matches.
	   Can be useful for excluding a specific subdirectory, for instance:
	   F:	net/
	   X:	net/ipv6/
	   matches all files in and below net excluding net/ipv6/
	K: Keyword perl extended regex pattern to match content in a
	   patch or file.  For instance:
	   K: of_get_profile
	      matches patches or files that contain "of_get_profile"
	   K: \b(printk|pr_(info|err))\b
	      matches patches or files that contain one or more of the words
	      printk, pr_info or pr_err
	   One regex pattern per line.  Multiple K: lines acceptable.

Note: For the hard of thinking, this list is meant to remain in alphabetical
order. If you could add yourselves to it in alphabetical order that would be
so much easier [Ed]

Maintainers List (try to look for most precise areas first)

		-----------------------------------

3C505 NETWORK DRIVER
M:	Philip Blundell <philb@gnu.org>
L:	netdev@vger.kernel.org
S:	Maintained
F:	drivers/net/3c505*

