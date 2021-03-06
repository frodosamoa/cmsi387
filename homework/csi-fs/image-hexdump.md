Hexdump of the image file
=========================

Here is the `hexdump` of the image file, let us specifying it!

	00000000  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*

The first big block under this text is the test disk's superblock. The first 32 bytes denote the inode count (in little endian). For our test disk it is 4. The second 32 bytes of the block denote the block count. For out test disk, it is `0x200`.

	00000400  40 00 00 00 00 02 00 00  19 00 00 00 e4 01 00 00  |@...............|
	00000410  35 00 00 00 01 00 00 00  00 00 00 00 00 00 00 00  |5...............|
	00000420  00 20 00 00 00 20 00 00  40 00 00 00 00 00 00 00  |. ... ..@.......|
	00000430  55 71 77 51 01 00 ff ff  53 ef 00 00 01 00 00 00  |UqwQ....S.......|
	00000440  34 71 77 51 00 00 00 00  00 00 00 00 01 00 00 00  |4qwQ............|
	00000450  00 00 00 00 0b 00 00 00  80 00 00 00 38 00 00 00  |............8...|
	00000460  02 00 00 00 01 00 00 00  c1 ba 87 e6 da ee 46 4b  |..............FK|
	00000470  8f e3 a5 e7 9d 85 b0 bb  00 00 00 00 00 00 00 00  |................|
	00000480  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	000004c0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 01 00  |................|
	000004d0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	000004e0  00 00 00 00 00 00 00 00  00 00 00 00 c3 10 ba 09  |................|
	000004f0  96 4c 49 78 81 1d 8e 81  61 8c 95 c5 01 00 00 00  |.LIx....a.......|
	00000500  0c 00 00 00 00 00 00 00  34 71 77 51 00 00 00 00  |........4qwQ....|
	00000510  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00000560  01 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	00000570  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*

Here is our first group. This lets us know that the inode table starts at the `6`. We take `6` and multiply it by the block size, `0x400`, and we get `0x1800`.

	00000800  04 00 00 00 05 00 00 00  06 00 00 00 e1 01 31 00  |..............1.|
	00000810  03 00 04 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	00000820  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001000  ff ff ff 3f 00 00 00 00  00 00 00 00 00 00 00 00  |...?............|
	00001010  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001030  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 80  |................|
	00001040  ff ff ff ff ff ff ff ff  ff ff ff ff ff ff ff ff  |................|
	*
	00001400  ff 7f 00 00 00 00 00 00  ff ff ff ff ff ff ff ff  |................|
	00001410  ff ff ff ff ff ff ff ff  ff ff ff ff ff ff ff ff  |................|
	*

The inode structure starts here. It says that our data begins in data block `10` which ends up being `3800`.

	00001800  00 00 00 00 00 00 00 00  34 71 77 51 34 71 77 51  |........4qwQ4qwQ|
	00001810  34 71 77 51 00 00 00 00  00 00 00 00 00 00 00 00  |4qwQ............|
	00001820  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001880  ed 41 e8 03 00 04 00 00  6a 78 77 51 20 77 77 51  |.A......jxwQ wwQ|
	00001890  20 77 77 51 00 00 00 00  e8 03 04 00 02 00 00 00  | wwQ............|
	000018a0  00 00 00 00 00 00 00 00  0e 00 00 00 00 00 00 00  |................|
	000018b0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001b00  80 81 00 00 00 30 04 04  34 71 77 51 34 71 77 51  |.....0..4qwQ4qwQ|
	00001b10  34 71 77 51 00 00 00 00  00 00 01 00 04 00 00 00  |4qwQ............|
	00001b20  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001b50  00 00 00 00 00 00 00 00  00 00 00 00 1b 00 00 00  |................|
	00001b60  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001d00  c0 41 00 00 00 30 00 00  34 71 77 51 34 71 77 51  |.A...0..4qwQ4qwQ|
	00001d10  34 71 77 51 00 00 00 00  00 00 02 00 18 00 00 00  |4qwQ............|
	00001d20  00 00 00 00 00 00 00 00  0f 00 00 00 10 00 00 00  |................|
	00001d30  11 00 00 00 12 00 00 00  13 00 00 00 14 00 00 00  |................|
	00001d40  15 00 00 00 16 00 00 00  17 00 00 00 18 00 00 00  |................|
	00001d50  19 00 00 00 1a 00 00 00  00 00 00 00 00 00 00 00  |................|
	00001d60  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*

Here is the inode for the `directory` folder.

	00001d80  fd 41 e8 03 00 04 00 00  6a 78 77 51 f8 76 77 51  |.A......jxwQ.vwQ|
	00001d90  f8 76 77 51 00 00 00 00  e8 03 02 00 02 00 00 00  |.vwQ............|
	00001da0  00 00 00 00 00 00 00 00  1c 00 00 00 00 00 00 00  |................|
	00001db0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001de0  00 00 00 00 da 7c e0 1c  00 00 00 00 00 00 00 00  |.....|..........|
	00001df0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|

Here is the inode for `text.txt`.

	00001e00  b4 81 e8 03 53 00 00 00  ac 76 77 51 ab 76 77 51  |....S....vwQ.vwQ|
	00001e10  ab 76 77 51 00 00 00 00  e8 03 01 00 02 00 00 00  |.vwQ............|
	00001e20  00 00 00 00 00 00 00 00  1d 00 00 00 00 00 00 00  |................|
	00001e30  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001e60  00 00 00 00 db 7c e0 1c  00 00 00 00 00 00 00 00  |.....|..........|
	00001e70  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|

Here is the inode for `text2.text`. The hard link links to this one also.

	00001e80  b4 81 e8 03 3b 00 00 00  21 77 77 51 20 77 77 51  |....;...!wwQ wwQ|
	00001e90  d4 76 77 51 00 00 00 00  e8 03 02 00 02 00 00 00  |.vwQ............|
	00001ea0  00 00 00 00 00 00 00 00  1e 00 00 00 00 00 00 00  |................|
	00001eb0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001ee0  00 00 00 00 dc 7c e0 1c  00 00 00 00 00 00 00 00  |.....|..........|
	00001ef0  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|

Here is the inode for the symbolic link of `text.txt`.

	00001f00  ff a1 e8 03 0b 00 00 00  51 78 77 51 f8 76 77 51  |........QxwQ.vwQ|
	00001f10  f8 76 77 51 00 00 00 00  e8 03 01 00 00 00 00 00  |.vwQ............|
	00001f20  00 00 00 00 00 00 00 00  2e 2e 2f 74 65 78 74 2e  |........../text.|
	00001f30  74 78 74 00 00 00 00 00  00 00 00 00 00 00 00 00  |txt.............|
	00001f40  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00001f60  00 00 00 00 dd 7c e0 1c  00 00 00 00 00 00 00 00  |.....|..........|
	00001f70  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*

Here are the directory entries for the files, links, and directories that I created. First we have the first directory entry for `directory`. It lists the files within in it which are the root directory `.`, then we have `..`, then `lost+found`, then `directory`, then `text.txt`, and lastly `text2.txt`.

	00003800  02 00 00 00 0c 00 01 02  2e 00 00 00 02 00 00 00  |................|
	00003810  0c 00 02 02 2e 2e 00 00  0b 00 00 00 14 00 0a 02  |................|
	00003820  6c 6f 73 74 2b 66 6f 75  6e 64 00 00 0c 00 00 00  |lost+found......|
	00003830  14 00 09 02 64 69 72 65  63 74 6f 72 79 00 00 00  |....directory...|
	00003840  0d 00 00 00 10 00 08 01  74 65 78 74 2e 74 78 74  |........text.txt|
	00003850  0e 00 00 00 b0 03 09 01  74 65 78 74 32 2e 74 78  |........text2.tx|
	00003860  74 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |t...............|
	00003870  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*

Here is the data block for the `lost+found` directory.

	00003c00  0b 00 00 00 0c 00 01 02  2e 00 00 00 02 00 00 00  |................|
	00003c10  f4 03 02 02 2e 2e 00 00  00 00 00 00 00 00 00 00  |................|
	00003c20  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00004000  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00004010  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00004400  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00004410  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00004800  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00004810  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00004c00  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00004c10  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00005000  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00005010  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00005400  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00005410  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00005800  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00005810  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00005c00  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00005c10  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00006000  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00006010  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00006400  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00006410  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00006800  00 00 00 00 00 04 00 00  00 00 00 00 00 00 00 00  |................|
	00006810  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00006c00  00 00 00 00 03 00 00 00  00 00 00 00 00 00 00 00  |................|
	00006c10  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*

This is the data block for the directory `directory`.

	00007000  0c 00 00 00 0c 00 01 02  2e 00 00 00 02 00 00 00  |................|
	00007010  0c 00 02 02 2e 2e 00 00  0e 00 00 00 14 00 09 01  |................|
	00007020  74 65 78 74 32 2e 74 78  74 00 00 00 0f 00 00 00  |text2.txt.......|
	00007030  d4 03 08 07 74 65 78 74  2e 74 78 74 00 00 00 00  |....text.txt....|
	00007040  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*

This is the data block for the text file `text.txt`.

	00007400  48 65 6c 6c 6f 21 20 54  68 69 73 20 69 73 20 61  |Hello! This is a|
	00007410  20 6e 6f 6e 2d 65 6d 70  74 79 20 74 65 78 74 20  | non-empty text |
	00007420  66 69 6c 65 20 61 74 20  74 68 65 20 74 6f 70 2d  |file at the top-|
	00007430  6c 65 76 65 6c 20 64 69  72 65 63 74 6f 72 79 20  |level directory |
	00007440  6f 66 20 74 68 65 20 66  69 6c 65 73 79 73 74 65  |of the filesyste|
	00007450  6d 2e 0a 00 00 00 00 00  00 00 00 00 00 00 00 00  |m...............|
	00007460  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*

This is the data block for the text file `text2.txt`.

	00007800  48 69 79 61 21 20 48 65  72 65 20 69 73 20 61 20  |Hiya! Here is a |
	00007810  6e 6f 6e 2d 65 6d 70 74  79 20 74 65 78 74 20 66  |non-empty text f|
	00007820  69 6c 65 20 69 6e 73 69  64 65 20 61 20 73 75 62  |ile inside a sub|
	00007830  64 69 72 65 63 74 6f 72  79 2e 0a 00 00 00 00 00  |directory.......|
	00007840  00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |................|
	*
	00080000