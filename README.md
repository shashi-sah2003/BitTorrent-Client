`Building BitTorrent`

1. `BitTorrent` is a protocol for downloading and distributing files across the internet.
It doesn't follow traditional client/server relationship, rather participants in the BitTorrent 
network, called peers, download pieces of files from each other, this makes it a 
`PEER-TO-PEER` protocol.

2. Centralized location for this network introduced `trackers`, which are central servers
that introduces peers to each other. They're just webservers running over HTTP.

3. A `.torrent` file describes the contents of a torrentable file and information for connecting to a tracker. It follows Bencode and we'll need to decode it.
Example of Bencoded data:
 - Strings: `4:spam` - spam
 - Integers: `i7e` - 7
 - Lists: `l4:spami7ee` - ['spam',7]
 - Dictionary: `d4:spami7ee` - {spam:7}
In this file only there is url of the tracker mentioned with announce 
