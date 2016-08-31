# TheDAOData
Data related to The DAO

This repository contains some scripts to retrieve data from The DAO on the Ethereum blockchain.

**Note** As @lyricalpolymath as found out when comparing his results with mine, my results are accurate to 9 decimal places. See https://github.com/bokkypoobah/TheDAOData/issues/2 . I won't revise my data as it is accurate enough at the moment.

**Update 09:44 Aug 31 2016 UTC**
I've uploaded v4 files with the rounding corrected by using BigNumber maths. The files are:

* [getTheDAOCreatedTokenEventsWithNonZeroExtraBalance_v4](https://github.com/bokkypoobah/TheDAOData/blob/master/getTheDAOCreatedTokenEventsWithNonZeroExtraBalance_v4)
* [CreatedTokenEventsWithNonZeroExtraBalance_v4.txt](https://github.com/bokkypoobah/TheDAOData/blob/master/CreatedTokenEventsWithNonZeroExtraBalance_v4.txt)
* [CreatedTokenEventsWithNonZeroExtraBalance_v4.xlsx](https://github.com/bokkypoobah/TheDAOData/blob/master/CreatedTokenEventsWithNonZeroExtraBalance_v4.xlsx)

<br />

### Get The DAO CreatedToken Event
The script `getTheDAOCreatedTokenEvents` can be used to retrieve The DAO CreatedToken events. The complete data extracted by this script can be found in `CreatedTokenEvents.txt`. Here's some sample data:

    address                                    amount to                                         blockHash                                                          blockNumber event        logIndex transactionHash                                                    transactionIndex
    0xbb9bc244d798123fde783fcc1c72d3bb8c189413      3 0xb504e60998c6f354a0794abd91d85e8bc8436211 0x031d5bac6154ca7616ac62e966da2b50a0aaa1b3bc24958ed9cb52d8c8fc1e2f     1429038 CreatedToken        3 0xc96b0f95a1e7e8c07cd488a05f20f9e8d4003fe8eea0ec7f7f4bf199af3198e1                9
    0xbb9bc244d798123fde783fcc1c72d3bb8c189413     50 0x53024f875bc85709af41d1c65c01fb4cc92d5c1c 0x48cf967fc94c2f808d82906c1a56e3e09abc99bb8279266fbace13963dc30a1f     1429053 CreatedToken        0 0x1e9ec3974b89653961cbd996d4f6cfc2845db977a3385761b99ed459c2464740                1
    0xbb9bc244d798123fde783fcc1c72d3bb8c189413     50 0x2680a6fe5957d177a9279450d2c040818a1949a8 0x40d4235ceb2da6c0288016596d7b55223afd4efce70ba3369e915c0d8a5aa0b1     1429085 CreatedToken        0 0xcea9c261931268d55e695449794bc73a1d614b069051cdd437c1db3d2b31ae0a                0

<br />

### Get The DAO Transfer Event
The script `getTheDAOTransferEvents` can be used to retrieve The DAO Transfer events. The incomplete data extracted by this script can be found in `TransferEvents.txt`. This is because The DAO transfers are still occurring. Here's some sample data:

    address                                     amount _from                                      _to                                        blockHash                                                          blockNumber event    logIndex transactionHash                                                    transactionIndex
    0xbb9bc244d798123fde783fcc1c72d3bb8c189413       5 0x198ef1ec325a96cc354c7266a038be8b5c558f67 0x428fbc00d1d36995f959f82690d9d16c66d643d2 0x26f05512b3a09ec8be28aa2a0810aa8fc725215d510f4836865c1e4ee0ef09e5     1599207 Transfer        0 0xe81c92ad910f44e6856f8db56a08d2ed771d2aeeed46844d3ba6fbdecffe9847                1
    0xbb9bc244d798123fde783fcc1c72d3bb8c189413 1000000 0x9cc04373e74f7dc7718d509025d12294656b328a 0x3507d25c89959890b598f7844e10a1ad482f3ffd 0x32aaafd1cabf518b3304a3333d9dd515a180e53606d6e98b2fe2c17c9c3e5342     1599208 Transfer        1 0x9137249f158563ed2829291552e7069a6e20d8fdd71d31e92c7c94c5fe05830b                1
    0xbb9bc244d798123fde783fcc1c72d3bb8c189413      20 0x8e3fc1ea5eeac9361b873355caa39f90c6b5ae06 0xfbb1b73c4f0bda4f67dca266ce6ef42f520fbb98 0x32aaafd1cabf518b3304a3333d9dd515a180e53606d6e98b2fe2c17c9c3e5342     1599208 Transfer        2 0x23d2fc74690bde686638d9c9f918340d39d3537912c0ed601cfb436789014c37                3
    
<br />

### The DAO CreatedToken Event Between Block 1520861 and 1599205 With Non-Zero Contribution To extraBalance Account

Script: [getTheDAOCreatedTokenEventsWithNonZeroExtraBalance_v3
](https://github.com/bokkypoobah/TheDAOData/blob/master/getTheDAOCreatedTokenEventsWithNonZeroExtraBalance_v3)

* As queried in the question [Question: how do you find the function hash "b61d27f6"](https://github.com/bokkypoobah/TheDAOData/issues/1), the function signature `0xb61d27f6` in the code represents the wallet contract `execute(address,uint256,bytes)` function.

Output - Tab Delimited: [CreatedTokenEventsWithNonZeroExtraBalance_v3.txt](https://github.com/bokkypoobah/TheDAOData/blob/master/CreatedTokenEventsWithNonZeroExtraBalance_v3.txt)

Output - XLSX: [CreatedTokenEventsWithNonZeroExtraBalance_v3.xlsx](https://github.com/bokkypoobah/TheDAOData/blob/master/CreatedTokenEventsWithNonZeroExtraBalance_v3.xlsx)

    Header	From	TokenOwner	CreatedBy	BlockNumber	TxHash	Timestamp	GMTDateTime	Amount	TheDAOAmount	extraBalanceAmount	TheDAOTokens	GasUsed	GasPrice	Cost	Nonce	Error
    Data	0x32be343b94f860124dc4fee278fdcbd38c102d88	0xbad9ab5fd55aff4a8aec47166e1a2894d68cc473	Proxy	1520861	0xb989cba5fad84d78e305909bf97605dc35b3cb6caf0e32a2009c3a2dda876003	1463302816	Sun, 15 May 2016 09:00:16 GMT	134	127.61904761904762	6.380952380952380953	12761.904761904761	83139	30000000000	0.00249417	64340	
    Data	0x44d7bd707d831f1cb9ae9fd6d129d56d3040564b	0x44d7bd707d831f1cb9ae9fd6d129d56d3040564b	Owner	1520866	0xf34ead2d5b1886e1b428082ff621aa2145e0f77b001011d1db99b15d356a26bf	1463302856	Sun, 15 May 2016 09:00:56 GMT	40	38.095238095238095	1.904761904761904762	3809.5238095238096	80960	21000000000	0.00170016	0	
    Data	0x7727b2afc5a6816452a455e65a6a7dd01d03af4b	0x7727b2afc5a6816452a455e65a6a7dd01d03af4b	Owner	1520866	0xafee9c83d41dd151b970f8241e27796db2aceaaace73bf1ecdc2dcc0f53a288f	1463302856	Sun, 15 May 2016 09:00:56 GMT	1	0.9523809523809523	0.04761904761904762	95.23809523809522	50960	20000000000	0.0010192	5	
    Data	0x3c7b53f4fa75cd9499bd593c37d5b9872151058a	0x3c7b53f4fa75cd9499bd593c37d5b9872151058a	Owner	1520870	0xaeca3a70346d726ac77ad598cc5e819acb644317a0bf33c81d2b6c3c8acdcc1a	1463302917	Sun, 15 May 2016 09:01:57 GMT	110	104.76190476190476	5.238095238095238096	10476.190476190475	80960	21000000000	0.00170016	5	
    Data	0xa8c8b89fd99a25b4a085dff3d967b47b10b37034	0xa8c8b89fd99a25b4a085dff3d967b47b10b37034	Owner	1520870	0xcc146aeea6d229dce6edd463c6d80fdd4e88af0a407ca6e9d72da31775eeb043	1463302917	Sun, 15 May 2016 09:01:57 GMT	0.01	0.009523809523809524	0.000476190476190477	0.9523809523809524	50960	20000000000	0.0010192	29	
    ...
    
For the reconcilation of my results against [Arachnid's results](https://github.com/arachnid/extrabalance/), see [ExtraBalanceReconciliation.md](https://github.com/bokkypoobah/TheDAOData/blob/master/ExtraBalanceReconciliation.md) .
    
For further information, see:
* [Which accounts contributed to The DAO's extraBalance account?](http://ethereum.stackexchange.com/questions/7390/which-accounts-contributed-to-the-daos-extrabalance-account)
* [How do I get a refund for the amount I paid in excess of 1 ether to 100 The DAO tokens](http://ethereum.stackexchange.com/questions/7265/how-do-i-get-a-refund-for-the-amount-i-paid-in-excess-of-1-ether-to-100-the-dao) for more details.
* The **ExtraBalance** section in [The DAO’s Edge Cases Multisig (Post Hard Fork)](https://medium.com/edge-cases-multisig-phf-official-channel/the-daos-edge-cases-multisig-post-hard-fork-2f107380bd61#.qdjyu4d9b).

<br />
<br />

Enjoy. (c) BokkyPooBah 2016. The MIT licence.
