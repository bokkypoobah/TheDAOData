# Extra Balance Reconcilation

@ledgerwatch in [thedao.slack.com/messages/extrabal_community](https://thedao.slack.com/messages/extrabal_community/) has deployed an **ExtraBalToken** contract to [0x5c40ef6f527f4fba68368774e6130ce6515123f2](http://etherscan.io/address/0x5c40ef6f527f4fba68368774e6130ce6515123f2#code) on the ETH chain in block [#2,197,120](http://etherscan.io/block/2197120) in transaction [0x6f5ea6f387722f2899789947a37703f211983b74215b0b15f5bb4b3835b63bc6](http://etherscan.io/tx/0x6f5ea6f387722f2899789947a37703f211983b74215b0b15f5bb4b3835b63bc6).

The script [reconcileExtraBalTokenValues](https://github.com/bokkypoobah/TheDAOData/blob/master/reconcileExtraBalTokenValues) has been written to reconcile the values in the **ExtraBalToken** contract with `TheDAO.CreateToken` events with non-zero `extraBalance` amounts.
