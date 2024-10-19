HashCheck Shell Extension - FAQ      

*   [Home](/ "Home")
*   [ContextConsole](/cmdopen/ "ContextConsole Shell Extension")
    *   [Main Page](/cmdopen/ "Main Page")
    *   [FAQ](/cmdopen/faq.html "Frequently Asked Questions")
    *   [Changelog](/cmdopen/changelog.html "Changelog")
*   [HashCheck](/hashcheck/ "HashCheck Shell Extension")
    *   [Main Page](/hashcheck/ "Main Page")
    *   [FAQ](/hashcheck/faq.html "Frequently Asked Questions")
    *   [Screenshots](/hashcheck/screenshots/ "Screenshots")
    *   [Changelog](/hashcheck/changelog.html "Changelog")
*   [NoRedirect](/noredirect/ "NoRedirect (Firefox Extension)")
    *   [Main Page](/noredirect/ "Main Page")
    *   [addons.mozilla.org](https://addons.mozilla.org/addon/11787 "NoRedirect @ addons.mozilla.org")
    *   [MozillaZine Thread](http://forums.mozillazine.org/viewtopic.php?t=1230675 "MozillaZine Forum Thread")
    *   [Changelog](/noredirect/changelog.html "Changelog")
*   [QuickDrag](/quickdrag/ "QuickDrag (Firefox Extension)")
    *   [Main Page](/quickdrag/ "Main Page")
    *   [addons.mozilla.org](https://addons.mozilla.org/addon/6912 "QuickDrag @ addons.mozilla.org")
    *   [FAQ](/quickdrag/faq.html "Frequently Asked Questions")
    *   [MozillaZine Thread](http://forums.mozillazine.org/viewtopic.php?t=644971 "MozillaZine Forum Thread")
    *   [Changelog](/quickdrag/changelog.html "Changelog")
*   [URLFlipper](/urlflipper/ "URL Flipper (Firefox Extension)")
    *   [Main Page](/urlflipper/ "Main Page")
    *   [addons.mozilla.org](https://addons.mozilla.org/addon/3572 "URL Flipper @ addons.mozilla.org")
    *   [Usage Guide](/urlflipper/usage.html "Usage Guide")
    *   [MozillaZine Thread](http://forums.mozillazine.org/viewtopic.php?t=669335 "MozillaZine Forum Thread")
    *   [Changelog](/urlflipper/changelog.html "Changelog")
*   [Misc](/misc/ "Miscellaneous Code")
    *   [Notepad2 Modifications](/misc/notepad2/ "Notepad2 Modifications")
    *   [addpath](/misc/addpath/ "addpath")
    *   [elevate](/misc/elevate/ "elevate")
    *   [fixiepng](/misc/fixiepng/ "fixiepng")
    *   [fontreg](/misc/fontreg/ "FontReg (Windows Font Registration Utility)")
    *   [hashutils](/misc/hashutils/ "hashutils")
    *   [hidecon](/misc/hidecon/ "hidecon")
    *   [hideexec](/misc/hideexec/ "hideexec")
    *   [inlinedisposition](/misc/inlinedisposition/ "InlineDisposition (Firefox Extension)")
    *   [pendmove](/misc/pendmove/ "pendmove")
    *   [resetwmi](/misc/resetwmi/ "resetwmi")
    *   [resizefile](/misc/resizefile/ "vcopy")
    *   [runinf](/misc/runinf/ "runinf")
    *   [stripshortname](/misc/stripshortname/ "runinf")
    *   [tabsubmit](/misc/tabsubmit/ "TabSubmit (Firefox Extension)")
    *   [timeclone](/misc/timeclone/ "timeclone")
    *   [vcopy](/misc/vcopy/ "vcopy")
    *   [vhdutils](/misc/vhdutils/ "vcopy")
    *   [winisoutils](/misc/winisoutils/ "winisoutils")
*   Archives
    *   [ClassicFox](/classicfox/ "ClassicFox (Firefox/Thunderbird Extension)")
    *   [kBlog](/kblog/ "kBlog (Blogging Platform)")
    *   [kComics](/kcomics/ "kComics (Comics Aggregator)")
    *   kJournal (discontinued)
    *   kPerl (discontinued)
*   Feedback
    *   [Bugs and Suggestions](/tracker/ "Submit Suggestions and Bug Reports")
    *   [E-mail Me](mailto:kliu@code.kliu.org "E-mail Me")
    *   [Donate](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=1533685 "Support code.kliu.org")
*   [About Me](http://www.kliu.org/about.html "About Me")

* * *

HashCheck Shell Extension - FAQ
===============================

* * *

[**<< Return to the main HashCheck page**](./)

* * *

Table of Contents

1.  [How do I install and uninstall the HashCheck Shell Extension?](#faq-install)
2.  [Can two _different_ files have the same checksum/hash?](#faq-unique)
3.  [What can I do with checksums/hashes?](#faq-uses)
4.  [What _can't_ I do with checksums/hashes?](#faq-misuses)
5.  [What algorithms and formats are supported?](#faq-algorithms)
6.  [Why is <insert algorithm here> not supported?](#faq-inclusion)
7.  [Can HashCheck be invoked from the command line?](#faq-command-line)
8.  [Why does the installer install two copies of the shell extension on 64-bit systems?](#faq-wow64)
9.  [What is the extended context menu?](#faq-ext-menu)

How do I install and uninstall the HashCheck Shell Extension?

To install, simply [download the installer](./#info-box), run it, and follow the on-screen instructions. Like most Windows software, this shell extension can be uninstalled using the program uninstallation applet found in the Windows Control Panel.

**For advanced users:** To run the installer in quiet (unattended) mode, invoke the installer with the `/quiet` command-line switch, and to extract the files to the current directory without installing, invoke the installer with the `/extract` command-line switch.

Can two _different_ files have the same checksum/hash?

Technically, yes, but for all practical intents and purposes, no. Since checksums digest a potentially infinite number of bits down to a small, finite number of bits, there will be "collisions". However, the likelihood of such collisions happening randomly is extremely low. Even for the "weakest" algorithm, CRC-32, the probability that, given a file, you will find a different file with the same checksum is 1 in 4 billion. For 128-bit checksums (MD4, MD5), the probability is an unfathomably small 1 in 340 billion billion billion billion, and for SHA-1, it is even smaller.

While random collisions are all but impossible, someone may try to specially craft a file that has the same checksum as another, different file. This is feasible (though it may be difficult, depending on the algorithm) with CRC-32, MD4, and MD5, but it is not feasible with SHA-1.

What can I do with checksums/hashes?

**Check for data corruption:** The most common use for checksums is to verify that data is intact and uncorrupted. It is often a good idea to check the checksum of a large download against a known, expected checksum to ensure that you have all the bytes and that there was no corruption in the transmission. Many file sharing applications use checksums to verify the integrity of each piece of data that it receives; with HashCheck, you can perform this sort of verification with anything that you download.

**Know if two files are the same:** Instead of directly comparing two files to see if they are the same, you can compare their checksums; this can be useful when it is not practical or convenient to directly compare two files.

**Know what files have changed:** If you create a checksum file of a collection of files, you have essentially taken a "fingerprint" of a "snapshot" of that data; if you take another such "fingerprint" later on, you can compare the two to see what files in the collection have been changed, added, and removed.

**_Limited_ authentication of data:** If you are using a "secure" algorithm (i.e., it is not feasible for someone to craft a different, malicious piece of data that has the same hash as a piece of good data; SHA-1 is secure) **_and_** you have a hash that is trustworthy, then you can use that to verify if a piece of data is trustworthy. Note that the second condition is very important: If someone has maliciously tampered with a piece of data, he could easily calculate a new checksum for the tampered data and feed that checksum to you. So in order for a checksum to be useful in verifying security, you must first be able to trust the checksum. For example, imagine a software publisher that tries to distribute a piece of software through a third-party mirror (which you do not trust) or through file sharing (which you trust even less) in an attempt to reduce bandwidth costs. If they post the hashes of their files on their own, reasonably trustworthy server, then you can use them to verify that what you downloaded from the untrustworthy third-party mirror is authentic.

What _can't_ I do with checksums/hashes?

**Authenticate data:** For true authenticity verification, you should look at public key cryptography and digital signatures because hashes can only validate data if the hash itself can be trusted, and the only way to fully establish the trust of a hash is to couple it with cryptography (which, effectively, is what a digital signature is).

**Recover or repair data:** Checksums can only tell you if data is corrupted; it cannot fix that corruption. For this, you need to couple checksums with redundancy data, such as Reed-Solomon codes (optical discs such as CDs make extensive use of such error-correction codes).

**Know what exactly has changed:** While checksums can tell you which files have been altered, it cannot how the content of each file has been altered; it is not a replacement for `diff`.

What algorithms and formats are supported?

HashCheck supports the [CRC-32](https://en.wikipedia.org/wiki/Cyclic_redundancy_check), [MD4](https://en.wikipedia.org/wiki/MD4), [MD5](https://en.wikipedia.org/wiki/MD5), and [SHA-1](https://en.wikipedia.org/wiki/SHA_hash_functions) algorithms.

HashCheck creates checksum files in the [SFV format](https://en.wikipedia.org/wiki/Simple_file_verification) for CRC-32, and in a format compatible with the output of the standard `md4sum`, `md5sum`, and `sha1sum` tools for the other algorithms; checksum files produced by HashCheck can be encoded in UTF-8, UTF-16LE, or the system's default ANSI code page.

HashCheck can read SFV checksum files as well as checksum files created by directing standard `md4sum`, `md5sum`, or `sha1sum` output to a file. It can detect and handle virtually any sort of character and line-ending encoding: UTF-8 (with or without signature), UTF-16LE/BE (with or without BOM), or the default ANSI code page on your system.

Why is <insert algorithm here> not supported?

Many algorithms are flexibly defined with respect to variables such as the desired output size (e.g., ranging from 224 bits to 512 bits for SHA-2) and the number of rounds used (e.g., 3 to 5 for HAVAL), which means that in order for the algorithm to be useful, the person creating the hash will have to specify these parameters, and most importantly, the person verifying the hash will have to know what parameters were used when creating the hash. This, along with the relative rarity of many of the algorithms out there, make them unsuitable for the intended use cases of HashCheck.† After all, you do not calculate a hash for a file just because you can—the hash has to be _useful_, which many of these are not.

† To detect non-malicious corruption and damage, 32-bit is adequate, 128-bit is overkill, and using anything greater than 160-bit demonstrates a lack of understanding of hashes and checksums. To protect against malicious corruption, SHA-1 is secure, and if you find that you need something stronger, then you should be looking at digitally signing your files instead of using HashCheck.

Can HashCheck be invoked from the command line?

As a shell extension, HashCheck was designed to be integrated into and invoked from Windows Explorer, so command-line support is very limited.

**Verifying a checksum file:** The following command will open a checksum file for verification in the HashCheck GUI:

`rundll32 %WinDir%\System32\ShellExt\HashCheck.dll HashVerify_RunDLL example.md5`

**Creating a checksum file:** HashCheck does not support the creation of checksum files from the command line, but you can use tools such as [hashutils](/misc/hashutils/) for this. For example:

`sha1sum *.zip > example.sha1`

Why does the installer install two copies of the shell extension on 64-bit systems?

Since shell extensions are run "in-process", a shell extension must be compiled to use the same CPU instruction set as its host process. For example, when you are running the 64-bit version of Windows Explorer, you will need the 64-bit version of the shell extension. If, however, you are using the shell extension from the _Open File_ dialog of Microsoft Office (which is a 32-bit process), then you will need the 32-bit version. Since you can run both 32-bit and 64-bit host processes, both the 32-bit and 64-bit versions of the shell extension need to be installed on 64-bit versions of Windows. Similarly, this is why 64-bit versions of Windows contain two versions of every system DLL: one for use by 32-bit processes, and one for use by 64-bit processes.

What is the extended context menu?

The extended context menu is the what you get when you hold down the `Shift` key while invoking the context menu in the Windows shell.

* * *

Page last modified on 2009/05/04.