# P2P-file-sharing
This is a multi-threaded peer-to-peer network code in Java for file distribution on similar lines of how BitTorrent functions.
Each client connects to the file owner to download a few chunks of the original file. 
Each of the participating clients (peers) then exchange these chunks among themselves until all the clients (peers) have a copy of the original file.
All operations are assumed to be implemented using a reliable transport protocol  (i.e.  TCP). The  interaction between  two  peers is  symmetrical:
Messages  sent in both directions look the same.
The  protocol  consists  of  a  handshake  followed by  a  never-ending  stream  of  length-prefixed messages. 
Whenever  a  connection  is  established  between  two  peers,  each  of  the  peers  of  the connection  sends  to  the  other  one  the  handshake  message  before  sending  other 
messages.

handshake and bitfield
Suppose that peer A tries to make a TCP connection to peer B. Here we describe thye behavior of peer A, but peer B should also fol
low the same procedure as peer A. After the TCP connection is established, peer A sends a handshake message to peer B. It also receives  a  handshake  message  from  peer  B  and  checks  whether  peer  B  is  the  right neighbor.  The  only  thing  to  do  is  to  check  whether  the  handshake  header  is  right  and the peer ID is the expected one.After  handshaking,  peer  A  sends  a‘bitfield’ message  to  let  peer  B  know  which file pieces  it  has.  Peer  B  will  also  send  its ‘bitfield’message  to  peer  A,  unless  it  has  no pieces. 

