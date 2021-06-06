# Pebblecoin
Pebblecoin    UPDATE 2015/12/31: Version 0.4.4.1 is now out.  The major change is optimizing the daemon to use less RAM.  It no longer keeps all the blocks, which are rarely needed, in RAM, and so RAM usage has decreased from around 2 gigabytes, to under 200 megabytes.  Mac binaries are also now available.  The new wallet is compatible with the old wallet - simply turn off the old wallet, and start the new wallet, and the blockchain will update automatically to use less RAM.  Code: Release Notes 0.4.4.1 - (All) Fix blockchain RAM usage, from almost 2 GB to less than 200 MB   - Seamless blockchain conversion on first run with new binaries - (Qt) Fix high CPU usage - (Qt) Fix sync indicator (# of total blocks) - (Mac) Mac binaries - Technical Notes:   - (All) Blockchain disk-backed storage with sqlite3 and stxxl   - (Mac) Fix mac compilation   - (All) Update build files &amp; instructions for linux, mac, windows   - (All) Remove unused protobuf and OpenSSL dependencies for Qt wallet   - (Tests) Fix valgrind errors   - (Tests) Use local directory for blockchain instead of default directory   - (Tests) Run tests on Windows if using new enough MSVC  LINKS: Windows 64-bit: https://www.dropbox.com/s/b4kubwwnb4t7o4w/pebblecoin-all-win32-x64-v0.4.4.1.zip?dl=0 Mac 64-bit: https://www.dropbox.com/s/uoy9z1oxu4x53cv/pebblecoin-all-mac-x64-v0.4.4.1.tar.gz?dl=0 Linux 64-bit: https://www.dropbox.com/s/jq3h3bc29jmndks/pebblecoin-all-linux-x64-v0.4.4.1.tar.gz?dl=0  Exchange: https://poloniex.com/exchange#btc_xpb .  Source: https://github.com/xpbcreator/pebblecoin/  CONTACT: xpbcreator@torguard.tg IRC: irc.freenode.net, #pebblecoin   UPDATE 2015/06/08: Version 0.4.3.1 is now out.  This is a minor, mostly bug-fix release.  Work continues on the next major release which will bring us user-created currencies and user-graded contracts. Release notes: Code: Release Notes 0.4.3.1 - RPC calls for DPOS:   - getdelegateinfos RPC call   - get kimageseqs RPC call   - block header contains signing_delegate_id - fix checkpoint rollback bug - fix inability to send coins if voting history was lost   UPDATE 2015/05/04: Version 0.4.2.2 is now out.  This is a bug-fix/cosmetic release.  Release notes: Payment ID support Windows installer Logos updated Improved DPOS tab Sync issues fully fixed Fix rare crash bug Fix min out 0 bug Fix debit display Fix GUI not updating Updated hard-coded seed nodes   UPDATE 2015/04/24: The switch-over to DPOS has succeeded without a hitch!  DPOS blocks are being signed as we speak, at the far faster pace of 15 seconds per block.  This marks the start of a new era for Pebblecoin.   UPDATE 2015/04/21: Congratulations to the first registered delegate!  This indicates the start of the forking change so everybody please update your daemons if you haven't already.    To promote the coin and encourage people to become delegates, we've come up with an incentive scheme.  First, we'll send a free 100 XPB to anybody who PMs me their public address, for people to play around with and to start using the coin.  Second, once DPOS starts, for the first month of DPOS I'll send an extra 0.5 XPB to the signing delegate for every block they process.  This is on top of the usual transaction fees they will receive.  This is to encourage more people to become delegates at this important phase of the coin.   UPDATE 2015/04/19: All went well on the testnet release, so after a few further minor modifications, we are releasing version 0.4.1.2 to the public.  This is a forking change, so please update your clients and servers (links below).  At block 83120, sometime on April 21st, registration for DPOS delegates will begin.  At block 85300, sometime on April 24th, the network will switch over to DPOS.  As with the testnet, to become a delegate and receive block fees for securing the network, just turn on your wallet, register to be a delegate (5 XPB fee), and then leave your wallet on.  It will sign the blocks when it is your turn.  While Roman works on the next phase of the release - introducing subcurrencies - I will be fixing up some loose ends on the wallet, adding payment ID support, etc.  This is truly an exciting time for Pebblecoin.  RELEASE NOTES: All clients adjust internal clocks using ntp (client list in src/common/ntp_time.cpp) Added testnet support DPOS registration starts Block 83120 (~April 21st) DPOS phase starts Block 85300 (~April 24th) Default fee bumped to 0.10 XPB Low-free transactions no longer get relayed by default Significantly improved wallet sync Checkpoint at Block 79000   TOTAL CURRENT COINS: Available at this link. BLOCK TARGET TIME: 2 minutes EXPECTED EMISSION: At Block 3600 (End of Day 5): ~78 XPBs At Block 6480 (End of Day 9): ~758 XPBs At Block 9360 (End of Day 13): 6,771.0 XPBs At Block 12240 (End of Day 17): ~61,000 XPBs At Block 15120 (End of Day 21): ~550,000 XPBs, start of regular 300/block emission At Block 21900 (End of Month 1): ~2,600,000 XPBs, 300/block At Block 43800 (End of Month 2): ~9,150,000 XPBs, 300/block At Block 85300 (End of POW phase): ~21,500,300 XPBs.   UPDATE: The Pebblecoin Pool is now live!   Instructions: Download the linux miner and run it: ./minerd -o stratum+tcp://69.60.113.21:3350 -u YOUR_WALLET_ADDRESS -p x   UPDATE: The Pebblecoin wallet is now live!     There have been thousands of attempts at alternative currencies in the community.  Many are 100% copies of existing blockchains with a different name.  Some are very slight variations with no significant differences.  From recent history it is apparent the only realistic chance for viability of a new currency is one that is innovation and continued support and development.  The bitcoin community for good reason has shown interest in currencies that provide privacy of transactions, several currencies such as darkcoin, have become popular based on this desire.  The best technology for privacy is cryptonote although for a variety of reasons there hasnt been much development for ease of use, and as a result there has not been significant adoption.  Pebblecoin (XPB) is a cryptonote based coin with improvements and changes in some areas, and the promise of development in others.  I invite developers to work on this technology with me.  There is no premine, any tips or support of any developer including myself will be completely voluntary.  These are the following areas which I have determined needs changes/updates: I welcome suggestions, and am interested what else I can try to improve.  1) New Mining algorithm (active)  A mining algorithm is either susceptible to ASIC development or to being botnetted, meaning it is either more efficient to have a centralized mining entity (as is the case with bitcoin) or to have an algorithm that requires a real CPU, in which case botnets become very attractive.  To my knowledge there does not exist a blockchain that attempts to solve both problems, by having an algorithm that only works on a general purpose computer and is difficult to botnet.  Cryptonote coins currently are primarily mined with botnets.  Boulderhash is a new mining algorithm requiring 13 GB RAM, nearly eliminating all possible zombie (botnet controlled) computers from mining.  Most infected computers in the world do not have 13 GB available, so an algorithm that requires that much RAM severely limits the productivity of a botnet.  13 GB also makes ASICs cost prohibitive, and the current GPUs do not have that much RAM.  What's left is general purpose computers as was the original intent of bitcoin's mining process.  2) Distribution of coins (active)  It is very common in the launch of a new cryptocurrency the distribution algorithm heavily is weighted towards the very early adopters.  Such distribution is designed to give a massive advantage to people who are fully prepared to mine at launch, with a very large difference shortly after sometimes a few days later.  If the point of mining is to both secure the network and fairly distribute coins a gradual build up of rewards makes more sense, with no drop off in mining rewards.  At a standard block reward of 300, at launch each block will reward 0.3 coins leading up to 3, 30, and finally the standard reward of 300 which will be the standard unchanging reward from that point.  It will take approximately 3 weeks for the block reward of 300 to be reached.  3) GUI Software (active)  There are no current cryptonote coins that have a downloadable GUI, which makes the user experience much worse than that of bitcoin.  It is hard to achieve signficant adoption with a command line interface.  The very first update had the exact GUI written for bitcoin fully working with Pebblecoin.  The GUI was released on Jan 19, before the full 300 XPB reward was awarded for winning the block.  4) IRC Chat support embedded in Client GUI (active)  For user support, and to talk to core developers message boards such as Bitcointalk and reddit are primarily used.  I have embedded an IRC client in the GUI and be available at set hours for any kind of support.   5) Address aliasing (to be worked on)  Just as a user visiting google does not need to know the ip address, similarly an address should have the ability to have an associated userid.  If I ask a friend to send me pebblecoins it would be easier to tell him send it to @myuserid rather than a very long address or scanning a QR code.  There should be a way of registering a userid on the blockchain that will permanently translate to a pebblecoin addresss.   QT INSTRUCTIONS: Download the package for your respective platform Run the Qt executable.  The software will generate a new wallet for you and use a default folder: ~/.pebblecoin on Linux and %appdata%\pebblecoin on Windows. To use an existing wallet, copy the wallet.keys file into the default folder. To use a different data directory and/or wallet file, run the software like so: ./pebblecoin-qt --data-dir &lt;DataDir> --wallet-file &lt;FileName>. To enable mining, run the start_mining_NEEDS_13GB_RAM.bat batch file. Or run the qt wallet with the --enable-boulderhash command line option, or put enable-boulderhash=1 into the config file.  It will start mining to the wallet address.  To change the number of mining threads (13GB required per thread), do --mining-threads &lt;NumThreads> or edit the batch file.  DAEMON + SIMPLEWALLET INSTRUCTIONS: Download the package, run: ./pebblecoind --data-dir pebblecoin_data Once the daemon finished syncing, run the simplewallet: ./simplewallet  POOL INSTRUCTIONS: Download the miner binary for your platform. Run the miner using a wallet address gotten from simplewallet or the Qt Wallet:  Code: minerd -o stratum+tcp://69.60.113.21:3350 -u YOUR_WALLET_ADDRESS -p x [/li]   DEV WALLET (for donations): PByFqCfuDRUPVsNrzrUXnuUdF7LpXsTTZXeq5cdHpJDogbJ8EBXopciN7DmQiGhLEo5ArA7dFqGga2A AhbRaZ2gL8jjp9VmYgk
