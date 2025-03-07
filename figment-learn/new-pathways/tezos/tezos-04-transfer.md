In this tutorial we will learn how to transfer an amount of Tezos tokens from our account to another account. Token transfers are the simplest function on most blockchains, and one of the most common.

The role of TezosToolkit here is to provide a simplified way of dealing with the lifecycle of an RPC request. It would be possible to implement the transfer functionality for ourselves, however it is preferable to utilize the toolkit for the flexible functionality and ease of use that it provides.

------------------------

# Challenge

{% hint style="tip" %}
In `pages/api/tezos/transfer.ts`, implement the function and try to make your first transfer on the Tezos network. You must replace the instances of `undefined` with working code to accomplish this.
{% endhint %}

**Take a few minutes to figure this out**

```typescript
//...
  try {
    const { mnemonic, email, password, secret, amount, recipient } = req.body
    const url = getTezosUrl();
    const tezos = new TezosToolkit(url);

    await importKey(undefined);

    // Call the transfer method

    // Await confirmation 
    await operation.confirmation(1) 

    res.status(200).json(operation.hash);
  }
//...
```

**Need some help?** Check out these links
* [**Transfer with Taquito**](https://tezostaquito.io/docs/quick_start/#transfer)
* [**Check out the `transfer` method's interface**](https://tezostaquito.io/typedoc/interfaces/_taquito_taquito.contractprovider.html#transfer)  

{% hint style="info" %}
You can [**join us on Discord**](https://discord.gg/fszyM7K), if you have questions or want help completing the tutorial.
{% endhint %}

Still not sure how to do this? No problem! The solution is below so you don't get stuck.

------------------------

# Solution

```typescript
//...
  try {
    const { mnemonic, email, password, secret, amount, recipient } = req.body;
    const url = getTezosUrl();
    const tezos = new TezosToolkit(url);

    await importKey(
      tezos,
      email,
      password,
      mnemonic,
      secret
    );

    const operation = await tezos.contract.transfer({ 
      to: recipient, 
      amount: amount 
    });

    await operation.confirmation(1);

    res.status(200).json(operation.hash);
  }
//...
```

**What happened in the code above?**

* First, we create a new `TezosToolkit` instance.
* Next, we import our wallet data using `importKey`.
* Next, we create an transaction using the method `transfer` of the `contract` module, passing:
  * The recipient address.
  * The amount in **μꜩ** (**mutez**).
* Then, we wait for the confirmation of the transaction.
* Finally, we send the `operation.hash` back to the client-side as JSON.

------------------------

# Make sure it works

Once you have the code above saved:
* Fill in the amount of **mutez** you want to send.
* Click on **Submit Transfer**.

![](../../../.gitbook/assets/pathways/tezos/tezos-transfer.gif)

-----------------------------

# Conclusion

Now that we have created our account and made a transfer, let's move on to deploying some code (known as a "smart contract") to the **Tezos** blockchain! Ready to take the plunge? Let's go... 
