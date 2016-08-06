# Extra Balance Reconcilation

The Extra Balance account holds the excess over 1 ETH = 100 DAOs that token purchasers paid in the last two weeks of The DAO's crowdfunding period.

The script [getTheDAOCreatedTokenEventsWithNonZeroExtraBalance_v3](https://github.com/bokkypoobah/TheDAOData/blob/master/getTheDAOCreatedTokenEventsWithNonZeroExtraBalance_v3) was used to generate the list of accounts contributing to the Extra Balance account. The Tab delimited output of this script is in [CreatedTokenEventsWithNonZeroExtraBalance_v3.txt](https://github.com/bokkypoobah/TheDAOData/blob/master/CreatedTokenEventsWithNonZeroExtraBalance_v3.txt).

An alternative method of generating the Extra Balance contribution data can be found at Arachnid's  [github.com/arachnid/extrabalance/](https://github.com/arachnid/extrabalance/). I copied the [extrabalance.json](https://github.com/Arachnid/extrabalance/blob/master/extrabalance.json) output from this repository and renamed it to [arachnid_extrabalance.json](https://github.com/bokkypoobah/TheDAOData/blob/master/arachnid_extrabalance.json). This data is referenced in the **ExtraBalance** section of [The DAO’s Edge Cases Multisig (Post Hard Fork)](https://medium.com/edge-cases-multisig-phf-official-channel/the-daos-edge-cases-multisig-post-hard-fork-2f107380bd61#.qdjyu4d9b)

I ran the reconciliation script [reconcileCreatedTokenEventsWithNonZeroExtraBalance_v3](https://github.com/bokkypoobah/TheDAOData/blob/master/reconcileCreatedTokenEventsWithNonZeroExtraBalance_v3) to generate the following results comparing my Extra Balance account contributions against Arachnid's calculations (the raw results can be found below):

<br />

---

# Reconciliation Of Arachnid's Results - Summary Of Differences

For the differences detailed in the next section, here is the summary.

    #          Arachnid     Etherscan   Difference
    ------ ------------  ------------ ------------
     1       0.52441835    0.49946081  -0.02495753
     2       0.72448254    0.49946081  -0.22502173
     3       0.56221045    0.23076923  -0.33144122
     4       0.74601404    0.13333333  -0.61268071
     5       0.00944670    0.00944670   0.00000000
     6       0.20000000    0.20000000   0.00000000
     7     124.16187229  124.49331351   0.33144122
     8       2.94313417    3.55581488   0.61268071
     9      11.85088003   11.88919432   0.03831430
    10       0.43567698    0.25000000  -0.18567698
    11      99.85263732  100.00000000   0.14736268
    12       5.74702074    5.99700000   0.24997926
    ------ ------------  ------------ ------------
    Total  247.75779361  247.75779361   0.00000000
    ------ ------------  ------------ ------------

<br />

---

# Reconciliation Results - Difference Details

All the accounts except the following matches between Arachnid's data and the data generated here. Note that BPB's data include some transaction that were <b>Out Of Gas</b> errors.:

<ol>

<li>
Account <a href="http://etherscan.io/address/0x006f4a5440c26fa045d6d253e14597b72999ee4f">0x006f4a5440c26fa045d6d253e14597b72999ee4f</a> A: 0.524418347209618 vs BPB: 0.649143936666667. <b>Should be 0.499460813333333334 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0xe290b5d4a4a0175a7bc535881eae4806fd04b060e56a966da71d52ef33de45ba">0xe290b5d4a4a0175a7bc535881eae4806fd04b060e56a966da71d52ef33de45ba</a> 0.149683123333333334 <b>Out of gas</b>
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xcb272e487c6d5a2eb2934b5393d1fcf5feb63cd5561793f5d3c253381c718de3">0xcb272e487c6d5a2eb2934b5393d1fcf5feb63cd5561793f5d3c253381c718de3</a> 0.499460813333333334 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x00b8f2209342369795b8388c40553933197c8a56">0x00b8f2209342369795b8388c40553933197c8a56</a> A: 0.724482542341536 vs BPB: 1.84903146333333. <b>Should be 0.499460813333333334 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0x321a5a6626ef34f779fec21439cfbc43ae0d92b9d1a15939003b79aee3a172ac">0x321a5a6626ef34f779fec21439cfbc43ae0d92b9d1a15939003b79aee3a172ac</a> 0.499460813333333334 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x5a0c4411e4092bc30a054b5f812013d4a526cdca95cd2ba75984b6db245758b7">0x5a0c4411e4092bc30a054b5f812013d4a526cdca95cd2ba75984b6db245758b7</a> 1.34957065 <b>Out of gas</b>
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x00c7d701fa374d9f26b3b09e9a3f6b766a38baff">0x00c7d701fa374d9f26b3b09e9a3f6b766a38baff</a> A: 0.562210447974399 vs BPB: 2.31794871794872. <b>Should be 0.23076923076923077 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0x50f3126d52b788c7cf748cae6611347839970f87daf57cfd846fc967acbcba2e">0x50f3126d52b788c7cf748cae6611347839970f87daf57cfd846fc967acbcba2e</a> 0.333333333333333334 <b>Out of gas</b>
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x2fa0d970b9e6e4453ac718bae74e3fcf57ea300a214f3c31454c62c428f55df2">0x2fa0d970b9e6e4453ac718bae74e3fcf57ea300a214f3c31454c62c428f55df2</a> 0.461538461538461539 <b>Out of gas</b>
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x3ed31ad3436918d1d75007b495e406340db4f84d9178b460d94150d7fc6cf345">0x3ed31ad3436918d1d75007b495e406340db4f84d9178b460d94150d7fc6cf345</a> 0.923076923076923077 <b>Out of gas</b>
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x4cf0d5de1b9d129271711dc316a43c2c6cadcdcb75f334298fbb44149982529e">0x4cf0d5de1b9d129271711dc316a43c2c6cadcdcb75f334298fbb44149982529e</a> 0.369230769230769231 <b>Out of gas</b>
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xbc347f525a622d788f91b2c034bf71925810fde4d765b83fab99c7a3977cd0c5">0xbc347f525a622d788f91b2c034bf71925810fde4d765b83fab99c7a3977cd0c5</a> 0.23076923076923077 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x00d9c9c5631bc25ee08be1c4c7ed8cbbb662d70b">0x00d9c9c5631bc25ee08be1c4c7ed8cbbb662d70b</a> A: 0.746014041113587 vs BPB: 2.13333333333333. <b>Should be 0.133333333333333334 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0xd20a95a9f051d6961ca766a9b2d0f18b6afdf6d8465931a3f70f2c4b1c023688">0xd20a95a9f051d6961ca766a9b2d0f18b6afdf6d8465931a3f70f2c4b1c023688</a> 2 <b>Out of gas</b>
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xda4d79d3efd0eede985b8604c78924e214f051095a18762443c8c28589e0be7f">0xda4d79d3efd0eede985b8604c78924e214f051095a18762443c8c28589e0be7f</a> 0.133333333333333334 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x00dc1ec1c5cd9bfef408aebe2e46e62a75148bac">0x00dc1ec1c5cd9bfef408aebe2e46e62a75148bac</a> A: 0.00944670476190476 vs BPB: 0.628416170151524. <b>Should be 0.009446704761904762 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0xc7cec8971425302cf34259ad55e1724f56282d34b7789b539b1c31082f8ebf74">0xc7cec8971425302cf34259ad55e1724f56282d34b7789b539b1c31082f8ebf74</a> 0.618969465389619048 <b>Out of gas</b>
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x9e1be8b2b4ae8e473d602fd4ba27dc061a7ea831d83e394a15139fb04df34a08">0x9e1be8b2b4ae8e473d602fd4ba27dc061a7ea831d83e394a15139fb04df34a08</a> 0.009446704761904762 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x00ff1d79e83997b205e7f0284f6f0502d75d979a">0x00ff1d79e83997b205e7f0284f6f0502d75d979a</a> A: 0.2 vs BPB: 4. <b>Should be 0.2 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0x0948845be17fb2cc4175b0504cb1e6fad3c410e178f78a528ccd0c026299f316">0x0948845be17fb2cc4175b0504cb1e6fad3c410e178f78a528ccd0c026299f316</a> 3.8 <b>Out of gas</b>
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x80b08ee15a6975b540d95d8e952f2732b548e1ce5383490a86290b4cf83bb423">0x80b08ee15a6975b540d95d8e952f2732b548e1ce5383490a86290b4cf83bb423</a> 0.2 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x0234978fa3c892dbded38c55a15ec9e11fa07059">0x0234978fa3c892dbded38c55a15ec9e11fa07059</a> A: 124.16187229499 vs BPB: 124.493313512195. <b>Should be 124.493313512195 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0xb9bd2e52a4cbca6e8d9e2a18529fc2e3b56f6dfac809e1bc826cd7f99a20fcc5">0xb9bd2e52a4cbca6e8d9e2a18529fc2e3b56f6dfac809e1bc826cd7f99a20fcc5</a> 58.389865236333333334 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xfa3848dc2cdd4da488bb8af3183372fc628dbe3cdae94f029df47d2679230d74">0xfa3848dc2cdd4da488bb8af3183372fc628dbe3cdae94f029df47d2679230d74</a> 22.034482758620689656 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xffb9a050b4e3936735912aeafdc668811e15ee65bc33b1decd88d774ef0093de">0xffb9a050b4e3936735912aeafdc668811e15ee65bc33b1decd88d774ef0093de</a> 22.034482758620689656 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x36cb02f92331745e3d5d7f2fc0cc795126e6d313a4ab0a9d9076cd20353c7c7c">0x36cb02f92331745e3d5d7f2fc0cc795126e6d313a4ab0a9d9076cd20353c7c7c</a> 22.034482758620689656 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x88a5c029687bb4fd865a13fb1fc06873c336cd97">0x88a5c029687bb4fd865a13fb1fc06873c336cd97</a> A: 2.94313417470251 vs BPB: 3.55581488248276. <b>Should be 3.55581488248276 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0x42fceda6fac87aa7c8cce09bbd84a234eda92717a2ca2dc2cfff496e31cf9c2b">0x42fceda6fac87aa7c8cce09bbd84a234eda92717a2ca2dc2cfff496e31cf9c2b</a> 1 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x98179a77510b8ab6f115268a12d1dc7a598b29f9b8dfecf2422f6f28414245b0">0x98179a77510b8ab6f115268a12d1dc7a598b29f9b8dfecf2422f6f28414245b0</a> 0.75 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xc971bb03a8a8053088eb330afafe7ea198d9fa23b87de73af9372b3d1c44e9f6">0xc971bb03a8a8053088eb330afafe7ea198d9fa23b87de73af9372b3d1c44e9f6</a> 0.25 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xa42be29ab8ec53118cc2457d34d0441a06bba68ac8b54b79544bf8e8750860f7">0xa42be29ab8ec53118cc2457d34d0441a06bba68ac8b54b79544bf8e8750860f7</a> 0.883258398 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x282eaead87e5674a6e7f079b255c94562ecc61062225fd37c682210875b8190e">0x282eaead87e5674a6e7f079b255c94562ecc61062225fd37c682210875b8190e</a> 0.672556484482758621 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x903f6b338a71d6f99f3c7dad541da317c63dbd0d">0x903f6b338a71d6f99f3c7dad541da317c63dbd0d</a> A: 11.8508800265313 vs BPB: 11.8891943233333. <b>Should be 11.8891943233333 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0x353056e0843b9f94090efa9974ae736c81142499aed6912991ddbffb7ed28d50">0x353056e0843b9f94090efa9974ae736c81142499aed6912991ddbffb7ed28d50</a> 4.333333333333333334 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x93f838bedab893f678b7956f85001487ed6ed695d746ba17cc6a29e9accab806">0x93f838bedab893f678b7956f85001487ed6ed695d746ba17cc6a29e9accab806</a> 0.333333333333333334 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xaa80b29ce002e294081ccaeab27cfb88ced6a323c68b300eb3f2bb86f8f4a68d">0xaa80b29ce002e294081ccaeab27cfb88ced6a323c68b300eb3f2bb86f8f4a68d</a> 0.222527656666666667 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x3f5edf94421742bb08d9262528955b06336bcf557528e377716039a87a0f5120">0x3f5edf94421742bb08d9262528955b06336bcf557528e377716039a87a0f5120</a> 0.333333333333333334
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x9a41d36bea806a8cbf38a4f793fc45c956239f6df4c77b2d4fb8ec6986208feb">0x9a41d36bea806a8cbf38a4f793fc45c956239f6df4c77b2d4fb8ec6986208feb</a> 6.666666666666666667 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0x9898ca78ed5253886fb9cdec33e6547db093f702">0x9898ca78ed5253886fb9cdec33e6547db093f702</a> A: 0.435676976810044 vs BPB: 0.437333333333333. <b>Should be 0.25 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0x64371cee1fa188205c4d8b6093862362e879bf02cb134a2eb5a2234f4d69314c">0x64371cee1fa188205c4d8b6093862362e879bf02cb134a2eb5a2234f4d69314c</a> 0.25 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x64c41b5d5dda2b96c394dc68e07e5bb2ffee4efd68390cf5d316f19231c51e35">0x64c41b5d5dda2b96c394dc68e07e5bb2ffee4efd68390cf5d316f19231c51e35</a> 0.187333333333333334 <b>Out of gas</b>
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0xe2b60cc130ec4416c95a0c38755fd0607140d1a8">0xe2b60cc130ec4416c95a0c38755fd0607140d1a8</a> A: 99.852637319992 vs BPB: 100. <b>Should be 100 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0xe75e7b1696de7399bef763f1a34d5b68f98b7ac7a3cc3cdc6fe0f74a329616ed">0xe75e7b1696de7399bef763f1a34d5b68f98b7ac7a3cc3cdc6fe0f74a329616ed</a> 16.666666666666666667 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x752b613d160059cb9a06c722341124cab2c454727a89e560e3c7ffc636b01ca8">0x752b613d160059cb9a06c722341124cab2c454727a89e560e3c7ffc636b01ca8</a> 16.666666666666666667 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x61dc55f46846d81460717d223e6a07a5fbfd7d02f404a02d233b8fb2ca49273b">0x61dc55f46846d81460717d223e6a07a5fbfd7d02f404a02d233b8fb2ca49273b</a> 16.666666666666666667 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x07adbb6d05ee4de3a41460ef3b1848c342834bb0cec4be234994173d56e3be5b">0x07adbb6d05ee4de3a41460ef3b1848c342834bb0cec4be234994173d56e3be5b</a> 16.666666666666666667 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x20ce6991f71c42b3254105283c7a3f5ef70da8bf871f79b504c9d7386723a25c">0x20ce6991f71c42b3254105283c7a3f5ef70da8bf871f79b504c9d7386723a25c</a> 16.666666666666666667 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xeb18e0d9a5631bb5d58eb3be89aa4db6980b6b074d37add1507a35695cc95861">0xeb18e0d9a5631bb5d58eb3be89aa4db6980b6b074d37add1507a35695cc95861</a> 16.666666666666666667 
  </li>
  </ol>
</li>

<li>
Account <a href="http://etherscan.io/address/0xff4663862a7fefceb4a0990bb1a45a9e738e55bd">0xff4663862a7fefceb4a0990bb1a45a9e738e55bd</a> A: 5.74702073711551 vs BPB: 5.997. <b>Should be 5.997 from Etherscan</b>
  <ol>
  <li>
  <a href="http://etherscan.io/tx/0x22ef628e7fee9b15e0c019ee3c9b507f70ed95957fc88aaedd634c20b85966c5">0x22ef628e7fee9b15e0c019ee3c9b507f70ed95957fc88aaedd634c20b85966c5</a> 0.033333333333333334 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x90946868ab572cc19995cba8c0f761ddf380450ad172ede470203592874739de">0x90946868ab572cc19995cba8c0f761ddf380450ad172ede470203592874739de</a> 0.000333333333333334 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x89027c149539e1661ddbca64ab48b293e23f314d601b6ab1cee0aeaa02ed0e78">0x89027c149539e1661ddbca64ab48b293e23f314d601b6ab1cee0aeaa02ed0e78</a> 0.266666666666666667 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x1419171f79a40c7c10f3fcdbcae385750b61142faa7a6f957574b82d302b6e2b">0x1419171f79a40c7c10f3fcdbcae385750b61142faa7a6f957574b82d302b6e2b</a> 0.333333333333333334 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xac335c079884c15837ffcf1d790f49422ae9adc3c1e0b99c7f6b82ebf101e419">0xac335c079884c15837ffcf1d790f49422ae9adc3c1e0b99c7f6b82ebf101e419</a> 5 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0xeda53577296d42b4f251c861de4c964d68f67b0f59f02eae03d9bd9f218d6ec5">0xeda53577296d42b4f251c861de4c964d68f67b0f59f02eae03d9bd9f218d6ec5</a> 0.03 
  </li>
  <li>
  <a href="http://etherscan.io/tx/0x718ea98d1cc7790727e7f0cdc432adc681beb384dc2a612aedc10dc7cc736274">0x718ea98d1cc7790727e7f0cdc432adc681beb384dc2a612aedc10dc7cc736274</a> 0.333333333333333334 
  </li>
  </ol>
</li>
</ol>

<ul>
  <li>Arachnid sum 344907.387187409</li>
  <li>BPB sum 344917.579923469 <b>Includes Out Of Gas errors</b></li>
  <li>Arachnid sum - BPB sum -10.1927360594273</li>
</ul>

<br />

---

# Raw Reconciliation Results

    NOT EQUALS 0x006f4a5440c26fa045d6d253e14597b72999ee4f = 0.524418347209618 vs 0.649143936666667
      0xe290b5d4a4a0175a7bc535881eae4806fd04b060e56a966da71d52ef33de45ba 0.149683123333333334 Out of gas
      0xcb272e487c6d5a2eb2934b5393d1fcf5feb63cd5561793f5d3c253381c718de3 0.499460813333333334 
    NOT EQUALS 0x00b8f2209342369795b8388c40553933197c8a56 = 0.724482542341536 vs 1.84903146333333
      0x321a5a6626ef34f779fec21439cfbc43ae0d92b9d1a15939003b79aee3a172ac 0.499460813333333334 
      0x5a0c4411e4092bc30a054b5f812013d4a526cdca95cd2ba75984b6db245758b7 1.34957065 Out of gas
    NOT EQUALS 0x00c7d701fa374d9f26b3b09e9a3f6b766a38baff = 0.562210447974399 vs 2.31794871794872
      0x50f3126d52b788c7cf748cae6611347839970f87daf57cfd846fc967acbcba2e 0.333333333333333334 Out of gas
      0x2fa0d970b9e6e4453ac718bae74e3fcf57ea300a214f3c31454c62c428f55df2 0.461538461538461539 Out of gas
      0x3ed31ad3436918d1d75007b495e406340db4f84d9178b460d94150d7fc6cf345 0.923076923076923077 Out of gas
      0x4cf0d5de1b9d129271711dc316a43c2c6cadcdcb75f334298fbb44149982529e 0.369230769230769231 Out of gas
      0xbc347f525a622d788f91b2c034bf71925810fde4d765b83fab99c7a3977cd0c5 0.23076923076923077 
    NOT EQUALS 0x00d9c9c5631bc25ee08be1c4c7ed8cbbb662d70b = 0.746014041113587 vs 2.13333333333333
      0xd20a95a9f051d6961ca766a9b2d0f18b6afdf6d8465931a3f70f2c4b1c023688 2 Out of gas
      0xda4d79d3efd0eede985b8604c78924e214f051095a18762443c8c28589e0be7f 0.133333333333333334 
    NOT EQUALS 0x00dc1ec1c5cd9bfef408aebe2e46e62a75148bac = 0.00944670476190476 vs 0.628416170151524
      0xc7cec8971425302cf34259ad55e1724f56282d34b7789b539b1c31082f8ebf74 0.618969465389619048 Out of gas
      0x9e1be8b2b4ae8e473d602fd4ba27dc061a7ea831d83e394a15139fb04df34a08 0.009446704761904762 
    NOT EQUALS 0x00ff1d79e83997b205e7f0284f6f0502d75d979a = 0.2 vs 4
      0x0948845be17fb2cc4175b0504cb1e6fad3c410e178f78a528ccd0c026299f316 3.8 Out of gas
      0x80b08ee15a6975b540d95d8e952f2732b548e1ce5383490a86290b4cf83bb423 0.2 
    NOT EQUALS 0x0234978fa3c892dbded38c55a15ec9e11fa07059 = 124.16187229499 vs 124.493313512195
      0xb9bd2e52a4cbca6e8d9e2a18529fc2e3b56f6dfac809e1bc826cd7f99a20fcc5 58.389865236333333334 
      0xfa3848dc2cdd4da488bb8af3183372fc628dbe3cdae94f029df47d2679230d74 22.034482758620689656 
      0xffb9a050b4e3936735912aeafdc668811e15ee65bc33b1decd88d774ef0093de 22.034482758620689656 
      0x36cb02f92331745e3d5d7f2fc0cc795126e6d313a4ab0a9d9076cd20353c7c7c 22.034482758620689656 
    NOT EQUALS 0x88a5c029687bb4fd865a13fb1fc06873c336cd97 = 2.94313417470251 vs 3.55581488248276
      0x42fceda6fac87aa7c8cce09bbd84a234eda92717a2ca2dc2cfff496e31cf9c2b 1 
      0x98179a77510b8ab6f115268a12d1dc7a598b29f9b8dfecf2422f6f28414245b0 0.75 
      0xc971bb03a8a8053088eb330afafe7ea198d9fa23b87de73af9372b3d1c44e9f6 0.25 
      0xa42be29ab8ec53118cc2457d34d0441a06bba68ac8b54b79544bf8e8750860f7 0.883258398 
      0x282eaead87e5674a6e7f079b255c94562ecc61062225fd37c682210875b8190e 0.672556484482758621 
    NOT EQUALS 0x903f6b338a71d6f99f3c7dad541da317c63dbd0d = 11.8508800265313 vs 11.8891943233333
      0x353056e0843b9f94090efa9974ae736c81142499aed6912991ddbffb7ed28d50 4.333333333333333334 
      0x93f838bedab893f678b7956f85001487ed6ed695d746ba17cc6a29e9accab806 0.333333333333333334 
      0xaa80b29ce002e294081ccaeab27cfb88ced6a323c68b300eb3f2bb86f8f4a68d 0.222527656666666667 
      0x3f5edf94421742bb08d9262528955b06336bcf557528e377716039a87a0f5120 0.333333333333333334 
      0x9a41d36bea806a8cbf38a4f793fc45c956239f6df4c77b2d4fb8ec6986208feb 6.666666666666666667 
    NOT EQUALS 0x9898ca78ed5253886fb9cdec33e6547db093f702 = 0.435676976810044 vs 0.437333333333333
      0x64371cee1fa188205c4d8b6093862362e879bf02cb134a2eb5a2234f4d69314c 0.25 
      0x64c41b5d5dda2b96c394dc68e07e5bb2ffee4efd68390cf5d316f19231c51e35 0.187333333333333334 Out of gas
    NOT EQUALS 0xe2b60cc130ec4416c95a0c38755fd0607140d1a8 = 99.852637319992 vs 100
      0xe75e7b1696de7399bef763f1a34d5b68f98b7ac7a3cc3cdc6fe0f74a329616ed 16.666666666666666667 
      0x752b613d160059cb9a06c722341124cab2c454727a89e560e3c7ffc636b01ca8 16.666666666666666667 
      0x61dc55f46846d81460717d223e6a07a5fbfd7d02f404a02d233b8fb2ca49273b 16.666666666666666667 
      0x07adbb6d05ee4de3a41460ef3b1848c342834bb0cec4be234994173d56e3be5b 16.666666666666666667 
      0x20ce6991f71c42b3254105283c7a3f5ef70da8bf871f79b504c9d7386723a25c 16.666666666666666667 
      0xeb18e0d9a5631bb5d58eb3be89aa4db6980b6b074d37add1507a35695cc95861 16.666666666666666667 
    NOT EQUALS 0xff4663862a7fefceb4a0990bb1a45a9e738e55bd = 5.74702073711551 vs 5.997
      0x22ef628e7fee9b15e0c019ee3c9b507f70ed95957fc88aaedd634c20b85966c5 0.033333333333333334 
      0x90946868ab572cc19995cba8c0f761ddf380450ad172ede470203592874739de 0.000333333333333334 
      0x89027c149539e1661ddbca64ab48b293e23f314d601b6ab1cee0aeaa02ed0e78 0.266666666666666667 
      0x1419171f79a40c7c10f3fcdbcae385750b61142faa7a6f957574b82d302b6e2b 0.333333333333333334 
      0xac335c079884c15837ffcf1d790f49422ae9adc3c1e0b99c7f6b82ebf101e419 5 
      0xeda53577296d42b4f251c861de4c964d68f67b0f59f02eae03d9bd9f218d6ec5 0.03 
      0x718ea98d1cc7790727e7f0cdc432adc681beb384dc2a612aedc10dc7cc736274 0.333333333333333334 
    Arachnid sum 344907.387187409
    BPB sum 344917.579923469
    Arachnid sum - BPB sum -10.1927360594273
