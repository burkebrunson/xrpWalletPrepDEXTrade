# A Guide to enabling Trading Functionality Through The XRPL Decentralized Exchange

---

> *A Report Submitted to the XRP Community in Partial Fulfillment of the Requirements for Understanding the XRPL DEX Capabilities*

**Compiled and Written by**	*Burke Brunson (a.k.a. Radiogenic) | [https://bit.ly/3hqKx7R](https://bit.ly/3hqKx7R)*

**Proofed and Edited by**	*Ponderjaunt |* [https://twitter.com/PonderJaunt](https://twitter.com/PonderJaunt)

This guide was compiled independently, without consultation with any named entity stated within. Unless otherwise amended, assume that this guide is NOT officially supported by any of the platforms mentioned below. Each platform has their own official documentation. This guide is an attempt to connect procedures from each platform, but these procedures may change at any point; users should expect that these procedures are experimental and that unforeseen risk exists within new technological services. Continue at your own risk. Please forgive any errors and omissions.

Distributed Everywhere and Nowhere; February, 2021 - XRPLD Version 1.7

## **Preface**

> *“Aller anfang ist schwer. Anfang ist anfang…”  - Mr. Robot*

[Recent U.S. enforcement action against Ripple and XRP](https://fortune.com/2020/12/21/ripple-to-be-sued-by-sec-cryptocurrency-xrp/) only highlights the distributed community’s need for one of the most important functionalities of the XRP Ledger:  [the On-Ledger Decentralized Exchange](https://xrpl.org/decentralized-exchange.html).Previously, and specifically since the [dissolution of RippleTrade](https://www.financemagnates.com/cryptocurrency/exchange/ripple-trade-closing-replaced-with-wallet-and-trading-portal-gatehub/), this functionality has received little attention from the community at large, and that ought to change immediately.

I encourage you to fact-check anything and everything that is put forward in this guide; do not blindly accept this information as correct -- double check each and every step before you follow it.

Before we begin, I am going to, as briefly as possible, cover some loose odds and ends that people should know of or have before proceeding with this guide.  If you require more information than what is provided here on a particular topic, I try to provide links where the information comes from or a hint of what web searches to perform.

However, it should be noted that this guide is really intended for those users who have at least the most basic experience purchasing digital assets on an exchange and transferring them to and from wallets *(particularly, XRP)*, a desire to use the XRP Ledger Decentralized Exchange, and a wish for someone to walk them through the Gateway trust lines and deposit process.Even if you fit into this intermediate-user category, I still suggest that you read the Preface *(or, at the minimum, skim it)*.  If you don’t fit into this category, and consider yourself new to the XRP ecosystem, it would be beneficial to understand this section before moving on. Continue independent research to better understand digital currencies, wallets, and exchanges, in the DLT space in general.Please note that only after doing your own due diligence and research should you return to this guide to better understand how to prepare to use the XRP Ledger Decentralized Exchange.

**What this guide is not:**

- This guide is not a comprehensive guide to understanding everything you ever wanted to know about digital currencies or XRP.
- This guide is not going to teach any trading mechanism functionality, such as setting DEX orders.

This guide is not financial advice; think of these writings as a “plain-english” recipe for financial inclusion.

An accompanying folder is included in the GitHub Repo called “imagesInReport” that contains the images in this document, along with some markings indicating some instructions.  The images are in order as they appear in the document, too, for ease of following along.

If any part of this document containing commentary and process connection was useful to you in completing this journey, please consider a one-time small donation of XRP to the author.  Such generosity would be greatly appreciated and a major help in his attempts to complete his own journeys.  The XRP wallet address and destination tag required to do so are:

**Burke Brunson**

XRP Address:  rhub8VRN55s94qWKDv6jmDy1pUykJzF3wq

Destination Tag:  989040096

*Kindly make sure the Destination Tag is included in your transaction; failure to do so means I will not receive the funds*.

[https://lh3.googleusercontent.com/oRsr9kM9XjtxEw0Vr3d6w9oQc7Usf8GlCLzWgLVsaNLOLaMQzLCba4GF6YVnjC_rviv24BP45Uon7Rml344TaIcAyVCVLSOOwi6IbVsD7Kzaz2dAsi86e5ZNoYlG64Yzmge500Mg](https://lh3.googleusercontent.com/oRsr9kM9XjtxEw0Vr3d6w9oQc7Usf8GlCLzWgLVsaNLOLaMQzLCba4GF6YVnjC_rviv24BP45Uon7Rml344TaIcAyVCVLSOOwi6IbVsD7Kzaz2dAsi86e5ZNoYlG64Yzmge500Mg)

## Disclaimer

***The content provided in this guide is for informational purposes only.** You should not construe any such information or other material as legal, tax, investment, financial, or other advice. Nothing contained in this guide constitutes a solicitation, recommendation, endorsement, or offer by the author or editor or any third party service provider to buy or sell any financial instruments in this or any other jurisdiction in which such solicitation or offer would be unlawful under the securities laws and applicable regulations of such jurisdiction. All content in this guide is information of a general nature and does not address the circumstances of any particular individual or entity. Nothing in the guide constitutes professional and/or financial advice, nor does any information in the guide constitute a comprehensive or complete statement of the matters discussed or the law relating thereto.Neither the author nor editor is a fiduciary by virtue of any person’s use of or access to the guide. You alone assume the sole responsibility of evaluating the merits and risks associated with the use of any information or other content included in this guide before making any decisions based on such information or other content.In exchange for using the information in this guide, you agree not to hold the author or editor, affiliates or any third party service provider liable for any possible claim for damages arising from any decision you make based on information or other content made available to you through this guide.*

*In short, this guide is intended for educational purposes to show people how to enable certain functionality on the XRPL, in the hopes that it will lead to another means of acquiring XRP for those who wish to do so (and nothing else).  What people choose to do with this knowledge is their business that neither the author nor proofreader are liable for in any way.*

## **Terminology**

### Abbreviations:

- **AML** = Anti-Money Laundering (AML refers to compliance of regulations and procedures intended to prevent criminals from disguising illegally obtained funds as legitimate income. This set of laws requires all financial businesses, such as exchanges, to comply with regulators to combat illicit uses of funds that mask the true nature of the activity that generated those funds.)
- **CEX** = Centralized Exchange
- **DEX** = Decentralized Exchange
- **DLT** = Distributed Ledger Technology
- **KYC** = Know Your Client/Customer procedures (The steps financial institutions must take to verify their customers' identities. Exchanges must follow and perform KYC practices to establish the identity of new clients when new accounts are created with them to utilize their services.)
- **XRP** = Digital Asset of the XRPL
- **XRPL** = XRP Ledger (a DLT Blockchain)
- **XRPL DEX** = XRP Ledger Decentralized Exchange (built-in asset exchange of XRPL)

### Definitions:

**Wallet :** A “wallet” in the context of this guide is a digital wallet that allows users to store and manage particular digital assets.

XRP wallets may also store unique cryptocurrencies and other digital assets that are “issued” (“Issuances;” see “Issued Currency” below) on the XRPL by any XRP wallet owner *(in this particular guide, the XRPL Gateways [see “XRPL Gateways” below] will be issuers.  For the purposes of this guide, an issued asset is the missing component that enables users to trade on the XRPL DEX [see “XRPL DEX” below])*.

**Please note:**  Any new XRP wallet requires a 20 XRP reserve to initialize a wallet’s active functionality.  Whenever you make your first deposit into your wallet, 20 XRP of that first deposit will be locked into the wallet’s reserve and be unavailable to transact *(In other words, you will want to have slightly more than 20 XRP as your first deposit to the wallet - this will initialize the wallet with the reserve *and* have some amount available beyond that 20 XRP available for transfer; once this is done, you’ll never have to worry about the reserve again, unless you want to delete the wallet and recover 15 of the 20 XRP)*.

More information on XRP wallet reserves can be found here:

- [https://xrpl.org/reserves.html](https://xrpl.org/reserves.html)

**Exchange :** An “Exchange” is a service that allows customers to trade currencies or assets.  It is important to note that this entity represents a point of *centralization* in the digital asset ecosystem.  If you need more information, web search for “digital asset exchange.”

**Decentralized Exchange :** A “Decentralized Exchange” is a type of exchange which allows for direct, peer-to-peer transactions to take place online securely and without the need for an intermediary (the online business/service described in the “Exchange” entry above).  In short, all trading functionality is handled by the distributed ledger; the typical third-party entities which would normally oversee the security and transfer of assets *(e.g. banks, stockbrokers, online payment gateways, government institutions, etc.)* are substituted by a distributed digital protocol with varying degrees of decentralization depending on how access to write information to a ledger is structured *(not all decentralized exchanges operate in the exact same manner)*.  If you need more information on this subject, web search for “decentralized exchange” or “DEX.”

**XRPL Gateways :** “XRPL Gateways” are the services that link the XRP Ledger to the rest of the world; specifically, Gateways are usually businesses/services that provide a way for money and other forms of value to move in and out of the XRP Ledger. While three types of Gateways exist, the ones we are concerned about in this guide are called “issuing” Gateways *(receives money or other assets of value outside of the XRP Ledger, and issues currency that can be transacted or traded in the XRP Ledger)*.  More information can be found here:

- [https://xrpl.org/become-an-xrp-ledger-gateway.html](https://xrpl.org/become-an-xrp-ledger-gateway.html)

**Issued Currency :** All currencies other than XRP can be represented in the XRP Ledger as “issued currencies.” These unique digital assets *(sometimes called ‘IOUs’ or “Issuances'')* are tracked in accounting relationships, called "trust lines," between addresses on the XRPL.  More information can be found here:

- [https://xrpl.org/issued-currencies-overview.html](https://xrpl.org/issued-currencies-overview.html)

**Trust Lines :** Issued currencies in the XRP Ledger often represent value held by gateways in the world outside the XRP Ledger. The address that issues those funds in the XRP Ledger is expected to pay the balance back, outside of the XRP Ledger, when users redeem their XRP Ledger balances by returning them to the issuer.  Since a computer program cannot force someone to keep a promise in the outside world, “trust lines” represent a way of configuring how much you trust an issuer to hold on your behalf.  More information can be found here:

- [https://xrpl.org/trust-lines-and-issuing.html](https://xrpl.org/trust-lines-and-issuing.html)

**XRPL DEX :** The XRP Ledger contains a fully functional decentralized exchange where users can trade issued currencies for XRP or against each other.  Amongst other intended uses, the “XRPL DEX” ensures that anyone able to deposit funds with a Gateway provider (per that provider’s particular instructions) can purchase XRP without any restrictions.  For more information, see these links:

- [https://xrpl.org/xrp-ledger-overview.html](https://xrpl.org/xrp-ledger-overview.html)
- [https://xrpl.org/decentralized-exchange.html](https://xrpl.org/decentralized-exchange.html)

## **Resources**

**Bithomp Paper Wallet Generator**

- [https://bithomp.com/paperwallet/](https://bithomp.com/paperwallet/)

**Ledger Nano X Hardware Wallet** (Affiliate Link)

- [https://bit.ly/2Maryot](https://bit.ly/2Maryot)

**GateHub**

- [https://gatehub.net/](https://gatehub.net/)

**Bitstamp**

- [https://www.bitstamp.net/](https://www.bitstamp.net/)

**Sologenic**

- [https://www.sologenic.com/](https://www.sologenic.com/)

**XRP Toolkit**

- [https://www.xrptoolkit.com](https://www.xrptoolkit.com/)

**XUMM**

- [https://xumm.app/](https://xumm.app/)

**XRPL**

- [https://xrpl.org/xrp-ledger-overview.html](https://xrpl.org/xrp-ledger-overview.html)

**XRPL DEX**

- [https://xrpl.org/decentralized-exchange.html](https://xrpl.org/decentralized-exchange.html)

**Customer Support Documentation**

**GateHub**

- [https://support.gatehub.net/hc/en-us/articles/360021318533](https://support.gatehub.net/hc/en-us/articles/360021318533-Register-a-GateHub-Account)

**XRPToolkit**

- [https://docs.xrptoolkit.com/what-is-xrp-toolkit](https://docs.xrptoolkit.com/what-is-xrp-toolkit)

## **Introduction**

Most people attempting to spot purchase digital assets are familiar with how to utilize a centralized exchange, or more commonly  an “exchange,” to do so.  These exchanges make the process of setting up an account *mostly painless*. However, onboarding funds onto the exchange, and subsequently, making a purchase of the asset(s) you wish to have *remains a somewhat complex process for many users.*Each centralized exchange (CEX) follows a similar type of workflow in order to onboard and make purchases.  Usually, the main difference one might find depends on whether the exchange uses a simple market price purchase interface or a slightly more complicated ‘pro’ trading interface, complete with charts and advanced order types *(futures contracts, or derivatives, of cryptocurrencies that enable margin trading get a bit trickier, but that is far beyond the scope of this guide anyway)*.However, there are major drawbacks to using a centralized exchange that can be solved by using a decentralized exchange (DEX).  The XRPL has a built-in DEX; to be frank - it is one of the most important functions of the XRPL and one reason why XRP may be valuable.

The XRPL DEX, similarly, makes the mechanic of purchasing or trading XRP and issued cryptocurrencies using available funds a rather simple process.  The major XRPL Gateway providers *(GateHub, Bitstamp, and Sologenic)* available today that offer access to XRPL DEX trading all utilize the familiar, advanced charting and order type interfaces and mechanics to enable a user to make their trades of available XRP and issued digital currencies, like the mechanic seen in many centralized exchanges.

Most people who have been around the blockchain space for any length of time know that DEXs are different from centralized exchanges, in that they enable a user to maintain cryptocurrencies in their own wallet while attempting to exchange them, as opposed to having to transfer those funds to an exchange’s wallet to participate in exchange markets.

This is, in fact, one of the major reasons why people should consider using DEXs instead of centralized exchanges.

Another incentive for a person to use a DEX is that it ensures anyone in the world who has appropriately configured access can exchange *any asset that is available* on the ledger with any other asset on the same ledger -- eventually the Interledger Protocol should connect separate ledgers together.  U.S. users can rejoice that access to XRP cannot be denied simply because CEXs have decided to limit access or delist the asset; access to XRP cannot be censored in the XRPL and, thus, on the XRPL DEX.

*However, what is not entirely clear for most first-time users of the XRPL DEX is the mechanism of making funds in their wallet available for use in trading in the first place.  I am convinced that this uncertainty is the primary reason most people choose to favor centralized exchanges and not use the XRPL DEX.*The community has asked for a detailed guide that adequately shows first-time XRPL DEX users how the deposit process with XRPL Gateway providers is different from the workflow they go through with a centralized exchange.

To accomplish this goal, I am going to discuss and illustrate this process regarding both Bitstamp Gateway and GateHub Gateway providers, as the two differ just slightly.  This nuance, once shown, should enable a person who is using any current or future XRPL Gateway provider to know and/or quickly determine the steps necessary to navigate that provider’s deposit and setup process for the XRPL.  I would encourage any user to, ultimately, set up accounts with different XRPL Gateway providers over time - doing so gives each user more flexibility.

In order to make use of this guide, you will want an account with one of the XRPL Gateway providers *(where you can send your deposit funds)* with a fully completed KYC verification process and an XRP wallet *(to which you own/have the private key)*.  I will briefly make mention of setting up a new XRP wallet (This requires a 20 XRP minimum reserve) using XUMM wallet app (the most convenient way to store and manage your crypto assets on the XRP Ledger), hardware wallets *(such as Ledger, an example I’ve personally used with success)*, and GateHub Wallet in this guide.

It is time!  Let’s begin.

---

## **Funding an XRP Wallet Pathway #1**

**Pathway #1** involves the use of a separate wallet generator *(XUMM, or you can substitute a hardware wallet in this step)*, XRPL Gateway servicer *(Bitstamp/Gatehub)*, and XRPL DEX access *(XRP Toolkit)*.  If you already have an XRP wallet *(to which you have the secret key)*, you can skip the XUMM wallet generator function by importing your existing XRP wallet - it’s your choice *(not advised if you have a wallet with a large amount of funds intended for long-term storage)*.

**Never share your secret key with a servicer that you don’t explicitly trust to handle that data in a secure way.**

- [https://support.xumm.app/hc/en-us/articles/360018136300](https://support.xumm.app/hc/en-us/articles/360018136300-Can-I-view-export-my-account-secret-#:~:text=Users%20won't%20be%20able,export%20your%20secret%20once%20imported.)

**Step 1 - Question: *Do you have an account set up with the XRPL Gateway provider (and KYC verification procedures finished)?***

*(If you already have a Bitstamp account *and* it is already verified, you can skip to “Step 2”.  You simply need to make a funds deposit to your account that is intended to be used in the Bitstamp Gateway.  If you do not have a Bitstamp account or if it is not already verified, read on.)*

First, ensure you have a Bitstamp account ([https://www.bitstamp.net/](https://www.bitstamp.net/)).  Click “Register” in the top right corner of the index page and follow instructions to set up the account.

[https://lh3.googleusercontent.com/xKO7_HBFYWH9EQ0Lgj6e0vPLsAx2sHhIpKgsN46pFVyWYYCMQ0OiDiiOkii3t_ZM8rU1bM2X-jcLnqRgKqvP3ZihyDDCPCEh0u52L92Y3PSW6Oh8-5oeofzRPwIIHYwFRy3AVEfB](https://lh3.googleusercontent.com/xKO7_HBFYWH9EQ0Lgj6e0vPLsAx2sHhIpKgsN46pFVyWYYCMQ0OiDiiOkii3t_ZM8rU1bM2X-jcLnqRgKqvP3ZihyDDCPCEh0u52L92Y3PSW6Oh8-5oeofzRPwIIHYwFRy3AVEfB)

After the account is set up, make sure you are logged in to the account and choose “Personal account verification“ *(you should see a prompt message for it on the first screen you see when you log in)*.  If you don’t see any message prompting you to verify the account, then you can do it manually.  After you log in, look to the top right of the screen; you should see a circular icon that represents you.  Click on that icon and go to “My information”.

[https://lh5.googleusercontent.com/60BSab7lHqB86W1ZLdrdf1ZaMAWWf51odbEMxxQRV6o0heIiuHS5hj14_E8akx_WyxlBpu9At2ZVy0Yx1o2g8Sw5lYvgWdj7mBVOzkWukHndkqlmxdiUpRwQ2vghUan1360fQ5Op](https://lh5.googleusercontent.com/60BSab7lHqB86W1ZLdrdf1ZaMAWWf51odbEMxxQRV6o0heIiuHS5hj14_E8akx_WyxlBpu9At2ZVy0Yx1o2g8Sw5lYvgWdj7mBVOzkWukHndkqlmxdiUpRwQ2vghUan1360fQ5Op)

In the first page that you come to *(“My Information”)*, you need to fill in the required fields.

[https://lh3.googleusercontent.com/jHoPsaRABcPFi_-y627xXJTzux46SCVqBS5mY6TNjonbqgYlVqVUTGIXpqCOMIZzzkIaEe7fdkZMBmNmP9nM-a0JYFeFnmfGg1Q-lEE57PbzpqChq0CdLzEREj7jFzvWbdcuK7yX](https://lh3.googleusercontent.com/jHoPsaRABcPFi_-y627xXJTzux46SCVqBS5mY6TNjonbqgYlVqVUTGIXpqCOMIZzzkIaEe7fdkZMBmNmP9nM-a0JYFeFnmfGg1Q-lEE57PbzpqChq0CdLzEREj7jFzvWbdcuK7yX)

Next, look at the section titled “Info and Documents''

*(under “My information”)*

.  That is where you will upload the files required for KYC verification.

[https://lh6.googleusercontent.com/9c1dMATZ3labS8EZn5Xrutwg7tQsuD0_mlA7PQEcvTMqq4lkXfHCqXhocPmq8XNusaKfSaz5QNLqD3FkJKUdOLAF-zOPuIl8eeR-SFTDm_DcrENfPYiaT9VkKQmzfaoFgTBu3K7J](https://lh6.googleusercontent.com/9c1dMATZ3labS8EZn5Xrutwg7tQsuD0_mlA7PQEcvTMqq4lkXfHCqXhocPmq8XNusaKfSaz5QNLqD3FkJKUdOLAF-zOPuIl8eeR-SFTDm_DcrENfPYiaT9VkKQmzfaoFgTBu3K7J)

Your account is not verified until you see the message “Account Status:  Verified'' on the “My Information” page.

[https://lh4.googleusercontent.com/aqOIPIs-eaRXZ30atMCmCeK3bh00GeVMYFP_MBHyerRSSlxFASY0gqzozy6g4O_smdEp9n8TuWUUisP4AcUoUqwaFn1427_LaxokyRK0llu8RpG7JzScPUI3SUdX_B0PpiHdU_v4](https://lh4.googleusercontent.com/aqOIPIs-eaRXZ30atMCmCeK3bh00GeVMYFP_MBHyerRSSlxFASY0gqzozy6g4O_smdEp9n8TuWUUisP4AcUoUqwaFn1427_LaxokyRK0llu8RpG7JzScPUI3SUdX_B0PpiHdU_v4)

Once you are verified, you will be able to make full use of the Bitstamp Gateway. Specifically, users will want verification to enter and exit fiat to and from the XRPL.

**Step 2 -  *Have you figured out the process required by that Gateway provider to deposit various types of funds with them, and done so?***

**U.S. Customers** **- *Please read the entire step before you proceed*.**  You will likely be making your first transfer to GateHub, not Bitstamp, in order to get your XRP wallet set up if you do not already have one with the minimum reserve already met.  After XRP wallet initialization, you can make transfers to Bitstamp without issue *(because you’ll be able to just do IOU assets via the Gateway and buy XRP that way).*

Hopefully, the current legal complaint brought by the SEC will be cleared up relatively soon and this pathway for market access will be less relevant, but it’s still a good thing to know, regardless, because it shows the strength of this asset class and its ecosystem moving forward.

*(If you already know how to deposit funds with Bitstamp and have done so, you can skip to “Step 3.”  As long as you have a positive balance showing for your account, you will be able to get IOU issuances done.)*

You can deposit funds to your account via a bank transfer, or purchase cryptocurrency directly with a credit or debit card -- limitations based on jurisdiction may apply.  U.S. customers may also use ACH to deposit funds to their accounts.To do this, log in to your Bitstamp account.  Go to “Deposit” on their navigation menu.  Choose Bank Transfer in the menu.

[https://lh3.googleusercontent.com/n8v8cfNizCCVAvqMTgU9U-u_dGkdKM1_YT1xivOTeTnm1lELsf8A9cKyFVERlhB7QjY9OrJFa8_mvWE-mrdVoBDwqYKEhR0q_XYnKJz8iEMzv82ZTbz29wHHyfLLKIrw5hlubFJg](https://lh3.googleusercontent.com/n8v8cfNizCCVAvqMTgU9U-u_dGkdKM1_YT1xivOTeTnm1lELsf8A9cKyFVERlhB7QjY9OrJFa8_mvWE-mrdVoBDwqYKEhR0q_XYnKJz8iEMzv82ZTbz29wHHyfLLKIrw5hlubFJg)

Select the currency you want to deposit and the balance you would like to credit it to *(if the balance differs from the deposited currency, the funds will be converted)*.  Follow the remainder of the instructions they provide to you.  If you have any questions about this process, you can see this specific help article:

- [https://www.bitstamp.net/faq/how-do-i-deposit-funds-to-my-bitstamp-account/](https://www.bitstamp.net/faq/how-do-i-deposit-funds-to-my-bitstamp-account/)

You can, of course, also transfer cryptocurrency you hold to Bitstamp, too, by initiating a transfer to the appropriate wallet address in a similar way as described above.

[https://lh6.googleusercontent.com/2LvKuKZAn1JOYjrTHCLe6ws6GnohIQjQkGpOglmKkHbbEfFdjuf6i4pIAQJYWr0PHuxpHxBY6LNDnlz88vnEz8fuoJ9eyiw_XkKLcfYjpVH5KDjy62_Kli13ILBwaN_mFpHHLKvn](https://lh6.googleusercontent.com/2LvKuKZAn1JOYjrTHCLe6ws6GnohIQjQkGpOglmKkHbbEfFdjuf6i4pIAQJYWr0PHuxpHxBY6LNDnlz88vnEz8fuoJ9eyiw_XkKLcfYjpVH5KDjy62_Kli13ILBwaN_mFpHHLKvn)

See this link below for more information:

- [https://www.bitstamp.net/faq/how-do-i-deposit-cryptocurrency-to-my-bitstamp-account/](https://www.bitstamp.net/faq/how-do-i-deposit-cryptocurrency-to-my-bitstamp-account/)

Once your account has funds in it, it is possible for you to purchase XRP directly through Bitstamp and, in step 3, send it to your XRP wallet *(which will also complete the activation process)* or to initiate an IOU issuance with the Bitstamp Gateway and send that to the XRP wallet.  Keep in mind that you’ll need to set trust lines first for any issued currency you want to transfer to your XRP wallet, so buying XRP first and transferring that is probably the best option here.  At this time, for all non-US customers, either option will work.**EVERYONE SHOULD READ THIS:** Unfortunately, US customers, at the moment, are unable to purchase XRP through Bitstamp.  The ‘catch-22’ situation here is, if you wanted to use the Bitstamp Gateway to transfer issued assets to your wallet so you could buy XRP on the DEX *(instead of just transferring XRP purchased through Bitstamp)*, *that would be completely possible, except it would be necessary to set the appropriate trust lines first - but, we can’t do that yet, because we don’t yet have any XRP in the wallet to set the trust lines*!This is a tough break at the moment for American consumers, which will hopefully be resolved soon so that XRP can be purchased directly through Bitstamp by U.S. customers again.  In the meantime there is a solution involving following pathway #2 *(GateHub)*, which will be a good idea for everyone to eventually do, anyway.  So, we can ‘kill two birds with one stone’ by setting up XRP purchases through GateHub and transferring the cryptocurrency to the wallet we set up in this specific pathway. Thus, we can turn a disadvantage into an advantage *(while highlighting why always having more than one option is so important!)*.

If you are a U.S. customer, read over step 3 to contemplate and determine which wallet you will choose, then switch over to pathway #2 to explore acquiring XRP.  Then, return to this guide once you’ve purchased it and are ready to fund and initialize your personal XRP wallet.

**Step 3 -  Question: *Do you have an XRP wallet initialized with the 20 XRP Reserve?***

*(If you already have a personal XRP wallet that you control, to which you have the secret key, and the wallet is already initialized with the 20 XRP reserve, you can skip to “Step 4.”)*

This guide is not really meant to effectively teach most users about digital asset or cryptocurrency wallets.  However, since a user must have an XRP wallet to trade on the XRPL DEX, one must be set up (if you don’t already have one).

**Option 1 - XUMM App or Bithomp Paper Wallet Generator**

Xumm is, perhaps, the most convenient way to create an XRP wallet to store and manage your crypto assets on the XRP Ledger *([https://xumm.app/](https://xumm.app/))*.

[https://lh5.googleusercontent.com/Y34RAaT1anTWhIRFLjXJlnWmfgEpGv99QFl09w78aDRY-8kexiU8rqWfGfKZdsbvzX_q4BjhW0jDnHw2NosG6EzinuKuNR_2kfZoU6Yhpx-vvetWyIOWK1nxCXrCabWwlnah1WMM](https://lh5.googleusercontent.com/Y34RAaT1anTWhIRFLjXJlnWmfgEpGv99QFl09w78aDRY-8kexiU8rqWfGfKZdsbvzX_q4BjhW0jDnHw2NosG6EzinuKuNR_2kfZoU6Yhpx-vvetWyIOWK1nxCXrCabWwlnah1WMM)

The app itself can generate XRP wallets, and doing so in this manner will allow you to skip the importing process of a paper wallet.  If you wish to have the secret key to the wallet for storage and safekeeping, the app can provide that information to you so you can copy it down to paper for storage -- this information is not stored on-site and will not be recoverable if you make a mistake in securing the phrases!  Generating your wallet this way will ensure you are prepared for the next step.

If you prefer, you can create an XRP “paper wallet.” Paper Wallets  As long as a person takes the necessary steps to secure the secret key *(the things you need to access and transact with digital assets)* of a paper wallet, these wallets may be incredibly digitally secure, but can be physically stolen, lost, or destroyed -- be warned of these physical attack vectors.	Visit this website *([https://bithomp.com/paperwallet/](https://bithomp.com/paperwallet/))*, press “Generate New Wallet,” click print, and follow the provided visual instructions.

[https://lh5.googleusercontent.com/8R9qSwaDYStJl4giI9lCRLJn_wuP4F5edXmAV8O2BmcinL4qANz34mSW48sasZjvn48rRqQKJOG2Reb56QekySrFWxKDMBCY3RhiYLmotFxQt48eu_bjixlHXm_3ZlasXhw8U7_X](https://lh5.googleusercontent.com/8R9qSwaDYStJl4giI9lCRLJn_wuP4F5edXmAV8O2BmcinL4qANz34mSW48sasZjvn48rRqQKJOG2Reb56QekySrFWxKDMBCY3RhiYLmotFxQt48eu_bjixlHXm_3ZlasXhw8U7_X)

Obviously, you’ll need a printer to do so.  It is possible to set up an XRP paper wallet without printing the page from that website; you simply write down the public “Address” and “Secret” key information on a separate sheet of paper *(Make sure you copy this down correctly and exactly or you will lose wallet access forever!)*.  More importantly, you should scan the QR code(s) that you see on the screen with a secure wallet app QR scanner to confirm they resolve your account.  A highly advantageous app to do this would, again, be XUMM.

**Option 2 - Hardware Wallets**

If you would prefer, you can purchase a hardware wallet from a number of third parties in order to create your XRP wallet.  Some people encourage the use of these wallets, instead, because they offer a way to manage numerous secret keys to multiple wallets *(which can even be different blockchains altogether)* without you having to copy/store them.  Consider this the hybrid digital-physical option. The hardware, or physical, part of the wallet is the device that stores secret keys *(similar to a paper wallet, secret keys are not on your computer or phone - nor are they usually connected to the internet)* and also assists a person in signing transactions.

I personally have had strong success using Ledger Nano X and S Wallets.  Despite the hack of the [Ledger Customer Information Database](https://www.coindesk.com/ledger-bitcoin-bounty-new-data-security-after-hack), the wallet itself has been incredibly secure.  I won’t explain how to set that up here; other guides exist on the web for that.  I will simply provide an affiliate link here ([https://bit.ly/2Maryot](https://bit.ly/2Maryot)) that can assist you in making the purchase of a Ledger Wallet, if you desire one; I encourage you to do your research first regarding hardware wallets.

[https://lh4.googleusercontent.com/-qENkAIoeCYfmtzmH3afrwxVorJDtGkIvXMrBSGxGwSacPA4y_UYokXCE_-ABnJviZRWSlsoXP08Mji3Qr0vMWieJIJvVnNsfhJO930a1tCkAQzT60Ix_Dbm1AS9U4Sv35yHpWRr](https://lh4.googleusercontent.com/-qENkAIoeCYfmtzmH3afrwxVorJDtGkIvXMrBSGxGwSacPA4y_UYokXCE_-ABnJviZRWSlsoXP08Mji3Qr0vMWieJIJvVnNsfhJO930a1tCkAQzT60Ix_Dbm1AS9U4Sv35yHpWRr)

You’ll need to wait for the wallet shipment to arrive to you in order to proceed with the rest of this guide.  As mentioned, other hardware wallets exist, and you can find them by doing a search for “Cryptocurrency hardware wallets.”  Make sure to check XRP Toolkit *(discussed later in this guide)* for determining compatibility of the brand if the one you are considering purchasing is not Ledger.  Once your hardware wallet arrives, take the necessary steps to set it up correctly and create an XRP wallet.

Now that you have an XRP wallet, you need to fund it with enough XRP to cover the 20 XRP reserve.  This will initialize the wallet and make it active.  After you purchase XRP, you can send it to this wallet using the public address information.Since this is a wallet you control, you will not need to supply a destination tag when transferring XRP to it, if you are asked for one *(note that, if you are sending assets to an XRP wallet you do not control, such as an exchange wallet, they may need you to supply the destination tag associated with your account; this is information they supply to you when depositing XRP)*.

**EVERYONE SHOULD READ THIS:** If you happen to be trying to get issued currencies in and out of Bitstamp, I ran into some confusion that I want to clear up here:Let’s assume for a moment that you would like to deposit some real USD with Bitstamp and have the Bitstamp Gateway process those funds and issue you a USD-IOU to your XRP wallet.  This same process is also possible with GateHub, discussed later, with an important distinction to be made.  Back to Bitstamp, though; the process for this is not entirely straightforward, at least in my opinion.  In regards to your bank deposit, you do not need to do anything special. You can deposit your funds to your Bitstamp account, just as you normally would to use their centralized exchange.Once you have a USD balance on your account, you can do with it as you please.  Should you wish Bitstamp Gateway to issue you a USD-IOU, you need to withdraw USD from your Bitstamp account *(which may seem strange to a first-time user)*, with one small difference - use this link:  [https://www.bitstamp.net/account/withdraw/ripple/](https://www.bitstamp.net/account/withdraw/ripple/).  You can also reach it by going to Withdraw --> IOU *(BTC, USD)*.

[https://lh6.googleusercontent.com/IIEQfZTvIfZSxCHmMuMLxcvYix3hg2LirQV7IyOHdOoc-yUza_ZdaygqdqalWMURbkNfbERw8Qv3HKL_uL4FyWBfCb0eTDqfM9YmR5FoAfVRHSgAeEdQEkeAVAQ8Vh4VtBkiwxo0](https://lh6.googleusercontent.com/IIEQfZTvIfZSxCHmMuMLxcvYix3hg2LirQV7IyOHdOoc-yUza_ZdaygqdqalWMURbkNfbERw8Qv3HKL_uL4FyWBfCb0eTDqfM9YmR5FoAfVRHSgAeEdQEkeAVAQ8Vh4VtBkiwxo0)

Do you understand what happened?  You placed real assets in trust with them via their preferred method of deposit, and they issued you an *IOU* to your XRP wallet by you requesting the withdrawal.	Similarly, if you were going to try to withdraw USD back into your bank account after using the USD-IOU on the XRPL, you would essentially need to do the opposite and deposit the USD-IOU to your Bitstamp account in the "Deposit" section - IOU *(BTC, USD)* tab, found at this link: [https://www.bitstamp.net/account/deposit/ripple/](https://www.bitstamp.net/account/deposit/ripple/).

[https://lh4.googleusercontent.com/GPbzwABmHtOF0KwIkaInA-33tPzL27GWg3EJxcv_yQHf9d--HTpogKgHCSv_fRFvyp3dzsQdSaoljvb_PYq6rplhiw4on0djDjazAUp_NwYpc_RJUQp3SOVIH6gtnJma7yuUGOzb](https://lh4.googleusercontent.com/GPbzwABmHtOF0KwIkaInA-33tPzL27GWg3EJxcv_yQHf9d--HTpogKgHCSv_fRFvyp3dzsQdSaoljvb_PYq6rplhiw4on0djDjazAUp_NwYpc_RJUQp3SOVIH6gtnJma7yuUGOzb)

Make sure to use the correct deposit address and destination tag for that IOU deposit.  In case you deposit USD-IOU back into your Bitstamp account, Bitstamp will credit it to your USD balance and you will then be able to withdraw real USD to your bank account or further use it to trade on your Bitstamp account.

**Step 4 -  Question: *Have you set up the appropriate trust line(s) between your XRP wallet and the wallet of the Gateway provider for each type of funds you plan to deposit with them?***

*(I am very excited about this step for you; you are about to see and use one of the coolest new additions to the XRP community.  I, not-facetiously, get goosebumps every time I open this website.)*

First, a quick aside about trust lines.  If you recall, the XRPL DEX allows you to trade two things:  XRP and issued currencies *(that may or may not represent real assets)*.  In order for your wallet to be able to hold and trade the issued currencies, you need to set up a trust line between your XRP wallet and the issuers XRP wallet for each type of issuance you want to interact with *(such as USD-IOU, EUR-IOU, BTC-IOU, etc.)*.Also, keep in mind that each Gateway *(GateHub, Bitstamp, etc.)* issues its own IOUs for any assets they operate with, so you will need to establish a new trust line for each Gateway’s USD-IOU, EUR-IOU, etc.  In this case, we are working with Bitstamp’s Gateway provider.If you wanted to transact in IOUs issued by the GateHub Gateway provider, and you already have trust lines set for Bitstamp’s Gateway providers, you would need additional trust lines *(to beat the dead horse - yes, even if you already have one Bitstamp USD-IOU trust line, you would need a GateHub USD-IOU trust line, too -- if the issuer wallets are different, but the currency codes are the same, the currencies are different)*.

Each trust line you establish costs 5 XRP that are added to your initial 20 XRP reserve *(just like the initial reserve, you can recover any trust line reserve you set up by, later, zeroing the balance of that asset from your wallet and cancelling the trust line; those 5 XRP will be released and available to you once again)*.

In this step, you will be importing your XRP wallet into the XRP Toolkit ([https://www.xrptoolkit.com](https://www.xrptoolkit.com/)), which will enable you to set the appropriate trust lines for your XRP wallet.  Once this is done, you will be able to interact with the XRPL DEX, which the XRP Toolkit provides a clean interface for.  The first thing to do is open the Toolkit hyperlink I provided.  On the index page, click on the link that says, “Get Started.”

[https://lh4.googleusercontent.com/FuwLNBijv-dJFg_Xeo63uOm6OLK1FDra55-rRE_AODyi6ECnNQo3mQNFwmkQy0IDcVQQrf2bKJ-IRpcFH0RkYiuRWE2Hz-K7Gckca9FQkC583q7OPIte8bb-frHrWaTrwnYpXpAD](https://lh4.googleusercontent.com/FuwLNBijv-dJFg_Xeo63uOm6OLK1FDra55-rRE_AODyi6ECnNQo3mQNFwmkQy0IDcVQQrf2bKJ-IRpcFH0RkYiuRWE2Hz-K7Gckca9FQkC583q7OPIte8bb-frHrWaTrwnYpXpAD)

On the next page you will see a bunch of information that shows you which hardware wallets can currently be integrated with the XRP Toolkit.

[https://lh6.googleusercontent.com/FCXmGK5NExGp6-rbRkRt_LKxcdUhE6Y_w2hHMrut7e9aFIILBFIa89jWM58hVMFqyXXnarbkyFg1vllRcfvkhKKgle2K2sDU1MuzvFCTtoJX0fQ2bVCuaLUDj6xlUmuIwMmnF8JV](https://lh6.googleusercontent.com/FCXmGK5NExGp6-rbRkRt_LKxcdUhE6Y_w2hHMrut7e9aFIILBFIa89jWM58hVMFqyXXnarbkyFg1vllRcfvkhKKgle2K2sDU1MuzvFCTtoJX0fQ2bVCuaLUDj6xlUmuIwMmnF8JV)

If you own a hardware wallet that is shown to be compatible, or if you have access to another XRP wallet to which you have the secret key, then you can click on “Connect Wallet.”  In the “Add Wallet” dialogue, select which type of wallet you have and follow the instructions provided.

[https://lh3.googleusercontent.com/sFhkqHTfakhwo1zWr24H449IEDMZTlK9JdsROJo3IuwJFTY_FccsmK2OCHeehkEWwst77HS10QrUbPyji8uzeWWTxJVd8CppkSyPtaKtyEa3ew_g5EON1M4JJKPgGQfwCQyvpdre](https://lh3.googleusercontent.com/sFhkqHTfakhwo1zWr24H449IEDMZTlK9JdsROJo3IuwJFTY_FccsmK2OCHeehkEWwst77HS10QrUbPyji8uzeWWTxJVd8CppkSyPtaKtyEa3ew_g5EON1M4JJKPgGQfwCQyvpdre)

During the integration setup, make sure that you grant whatever advanced authentication permissions are required by your browser to allow the wallet integration to proceed correctly.

Once your wallet is integrated into the XRP Toolkit website, you’ll be brought to the ‘User Interface Overview’ screen that provides you with a dashboard for the XRP wallet.  You’ll notice a navigation menu in the top left, an account switcher in the top right *(with a link to the XRP Toolkit Documentation to the left of it - [https://docs.xrptoolkit.com/what-is-xrp-toolkit](https://docs.xrptoolkit.com/what-is-xrp-toolkit))*, and the Content Area below.

[https://lh3.googleusercontent.com/NfnNg4XpS0GLpKMpR5dYWAOWPszUWvY_fyZhAz7q4tS-b7omwk-TOwPaPpzRddWSAY94elbmVE7IsRXFXul9ocrPhthlhU7RMJuxY6ZeAbLGiDbZOoT2fNSWqF-7k0trsGO-fhr2](https://lh3.googleusercontent.com/NfnNg4XpS0GLpKMpR5dYWAOWPszUWvY_fyZhAz7q4tS-b7omwk-TOwPaPpzRddWSAY94elbmVE7IsRXFXul9ocrPhthlhU7RMJuxY6ZeAbLGiDbZOoT2fNSWqF-7k0trsGO-fhr2)

While there is much to explore here, you should first use this toolkit to get your trust lines set up for your XRP wallet.

First, make sure that you have enough XRP in your wallet beyond the 20 needed for the minimum reserve requirement; again, you’ll need 5 additional XRP per trust line you wish to set.Go to the Navigation Menu -> Hover over Account -> Select “Assets'' in the drop-down menu.

[https://lh5.googleusercontent.com/Ck-GvNRIJdmARytw4SrpQiCSSRXyW8BUhhLcqIgNR0zXU0l2zzKv3bMpOyqyiiurFF_qu2_WSRJH24U6GkrbAi1DJ-laRd1ccV03TpMAnKOhgCsZo4AH5X5nVdtDIrAurSZpOei1](https://lh5.googleusercontent.com/Ck-GvNRIJdmARytw4SrpQiCSSRXyW8BUhhLcqIgNR0zXU0l2zzKv3bMpOyqyiiurFF_qu2_WSRJH24U6GkrbAi1DJ-laRd1ccV03TpMAnKOhgCsZo4AH5X5nVdtDIrAurSZpOei1)

In the Add Asset form on the Assets page, select the Issuance you'd like to be able to hold and receive from other accounts.

[https://lh3.googleusercontent.com/Pb7re74m9bvPnS2BjRNfTKHFiFk2AsGS2LcnyD-McM9YdqyWRazi1zi_LxkU9MNHrlglsfYIzxA9o3kRLoWcwVcew6UdDNYiOc8p2IEVG2j-FG7xQpJ4nD_gyUlbuFZhLPbOzJvi](https://lh3.googleusercontent.com/Pb7re74m9bvPnS2BjRNfTKHFiFk2AsGS2LcnyD-McM9YdqyWRazi1zi_LxkU9MNHrlglsfYIzxA9o3kRLoWcwVcew6UdDNYiOc8p2IEVG2j-FG7xQpJ4nD_gyUlbuFZhLPbOzJvi)

The options pre-populated by XRP Toolkit in the drop-down menu there are considered to be from reputable sources *(you’ll notice that Bitstamp USD and Bitstamp BTC are two options)*.  Select one of those two options and decide if the pre-populated limit value of the trust line is agreeable to you; if you would prefer to trust that source with a different amount, change the number as desired.

[https://lh5.googleusercontent.com/prtJBXer-PBcy1083mFHN732jGyWAA4ome_BvZQTLeAzmilRlABeOOK8sl6QUBwFrAx4yY7rUk9ICGSZAb0gyzRybK8zLAwpLnPqS4jF5tTTomxEJVBBlRVhQIsCb_8nA09e6jNG](https://lh5.googleusercontent.com/prtJBXer-PBcy1083mFHN732jGyWAA4ome_BvZQTLeAzmilRlABeOOK8sl6QUBwFrAx4yY7rUk9ICGSZAb0gyzRybK8zLAwpLnPqS4jF5tTTomxEJVBBlRVhQIsCb_8nA09e6jNG)

Click “Next.”  Use your chosen transaction signing app or hardware to proceed with the trust line set transaction.  The added asset will appear in the Trusted Assets table on the current Assets page and on the Overview page. You can now hold and receive the added asset.

As of this moment, you are now completely set to exchange currencies on the XRPL DEX with this XRP wallet that you established with either XUMM, Bithomp Paper Wallet Generator, or a Hardware Wallet -- Congratulations!

You can now interact with the DEX by going to the Navigation menu and clicking “Trade.”

[https://lh6.googleusercontent.com/AAaWOFhGheFcFXxUJHjSwEYbj0Jn15Y8zG0QIfuXFNUFnwnQ-3vY6TAcFQCBEv9cwzMdwj7oLuBsCJsAeD_PRFC0z39aswQhPu-KQgRBLep90Qap8IpZpOeZGohV6Cr1Urf7hrF7](https://lh6.googleusercontent.com/AAaWOFhGheFcFXxUJHjSwEYbj0Jn15Y8zG0QIfuXFNUFnwnQ-3vY6TAcFQCBEv9cwzMdwj7oLuBsCJsAeD_PRFC0z39aswQhPu-KQgRBLep90Qap8IpZpOeZGohV6Cr1Urf7hrF7)

The mechanics of how to set custom trust lines are also covered in other guides available on both XRP Toolkit and GateHub.If you have any other questions regarding how to use XRP Toolkit to get the trust lines set up in order to use the DEX or to get the IOUs of the assets you are depositing with Bitstamp into your XRP wallet, I absolutely suggest you read the Bitstamp and XRP Toolkit Support Documentation provided here:

- [https://www.bitstamp.net/faq/how-do-i-deposit-funds-to-my-bitstamp-account/](https://www.bitstamp.net/faq/how-do-i-deposit-funds-to-my-bitstamp-account/)
- [https://www.bitstamp.net/faq/ripple-btc-usd-withdrawals/](https://www.bitstamp.net/faq/ripple-btc-usd-withdrawals/)
- [https://www.bitstamp.net/faq/iou-btc-usd-deposit/](https://www.bitstamp.net/faq/iou-btc-usd-deposit/)
- [https://support.gatehub.net/hc/en-us/articles/360021318533](https://support.gatehub.net/hc/en-us/articles/360021318533-Register-a-GateHub-Account)

You can sift through the different topics on the left sidebar and find answers to questions you have.

*(You can actually still use GateHub to access XRPL DEX trading even if you use XRP Toolkit to create your XRP wallet!  In other words, it is available to you, regardless of which pathway you go through to make an XRP wallet.  You would simply import your XRP wallet made with XUMM into GateHub.  That fact should actually encourage you to follow pathway #2 as well, even if you don’t set up a separate XRP wallet for that service.)*

## **Funding an XRP Wallet Pathway #2**

Pathway #2 will involve a Gateway service *(GateHub)* that can perform all of the necessary steps (wallet generation, funds deposit, trust line creation, and XRPL DEX trading) within its web service.  If you already have an XRP wallet *(to which you have the secret key)*, you can skip the GateHub wallet generator function by importing your existing XRP wallet - it’s your choice *(This is not advised if you have a wallet with a large amount of funds intended for long-term storage)*.

**Step 1 -  *Do you have an account set up with the XRPL Gateway provider (and KYC verification procedures finished)?***

*(If you already have a GateHub account *and* it is already verified, you can skip to “Step 2”.  You simply need to make a funds deposit to your account that is intended to be used in the GateHub Gateway.  If you do not have a GateHub account or if it is not already verified, read on.)*

First, ensure you have a GateHub account ([https://gatehub.net/](https://gatehub.net/)).  Click “Sign Up” in the top right corner of the index page and follow instructions to set up the account.

[https://lh4.googleusercontent.com/hTMd7hjFKYOTEFyePNHzI6btf5O3M2zuejgepQIEEFc4T1KMMjqkuIdhk-RTitrsrVJTU7rvX1txPehIvJ4oMxNauE6qdGa4wqi4XQHOxgXNjuE2Vun8rE3SWke-E8j6ljl3d_jw](https://lh4.googleusercontent.com/hTMd7hjFKYOTEFyePNHzI6btf5O3M2zuejgepQIEEFc4T1KMMjqkuIdhk-RTitrsrVJTU7rvX1txPehIvJ4oMxNauE6qdGa4wqi4XQHOxgXNjuE2Vun8rE3SWke-E8j6ljl3d_jw)

After the account is set up, make sure you are logged in to the account and look to the top right of the screen; you should see a bell icon and another icon to the right of that.

[https://lh5.googleusercontent.com/h1tqy_darn118oHCbjIMvDdMyAhvxgCdNrVx4HsZVKuir8h2msqGocnB6brws82rats2BB1usvN8eXs1UY6CoeSsjAxc_oiELmCz9bBdrCSjd2B23sFI2G1iXElkEI_jX_-Qw3sC](https://lh5.googleusercontent.com/h1tqy_darn118oHCbjIMvDdMyAhvxgCdNrVx4HsZVKuir8h2msqGocnB6brws82rats2BB1usvN8eXs1UY6CoeSsjAxc_oiELmCz9bBdrCSjd2B23sFI2G1iXElkEI_jX_-Qw3sC)

Click on the icon to the right of the bell and go to “Personal Details.”  In the first page that you come to *(“Settings” -> “Identity”)*, look at the section titled “Documents.”  That is where you will upload the files required for KYC verification.  Obviously, you should also fill out all of the other applicable personal information on that page.

[https://lh6.googleusercontent.com/zjr4u9E9qAyPFCjY8t68pAtcuzGaW3iNCnmiN0B2cvruQ-Y_9h2NerTEFsm-sjF7HtDKIvZS6w4-6f3zS2ADD5MAkXFpYpQcsB_SqJOu3AdWEVr3n5ZDXlBe33T02EfXLky_MAiA](https://lh6.googleusercontent.com/zjr4u9E9qAyPFCjY8t68pAtcuzGaW3iNCnmiN0B2cvruQ-Y_9h2NerTEFsm-sjF7HtDKIvZS6w4-6f3zS2ADD5MAkXFpYpQcsB_SqJOu3AdWEVr3n5ZDXlBe33T02EfXLky_MAiA)

Finally, you’ll need to, after you upload your “documents,” try to connect to the available Gateways on GateHub by clicking on the Gateways tab *(2 to the right from “Identity”)*.  You are not confirmed until you are able to connect to those Gateways and are “Accepted.”

[https://lh5.googleusercontent.com/FYYH1Hsxiw22rFB_czSelQd1IvTKVDCN0WpEMLJF14UG43A-uPrjZRfUmfkq3LHDWAoYIt-WN617LKNCA0BKs2fZp_rrGN8G7APPgoyybWz8d5K72xxETth7BWmZRJGnc-roQlzB](https://lh5.googleusercontent.com/FYYH1Hsxiw22rFB_czSelQd1IvTKVDCN0WpEMLJF14UG43A-uPrjZRfUmfkq3LHDWAoYIt-WN617LKNCA0BKs2fZp_rrGN8G7APPgoyybWz8d5K72xxETth7BWmZRJGnc-roQlzB)

**Step 2 -  Question: *Do you have an XRP wallet initialized with the 20 XRP Reserve?  Have you figured out the process required by a Gateway provider to deposit various assets with them and have you done so?***

*(If you already have a personal XRP wallet imported into GateHub [by owning the secret key] *and* the wallet is already initialized with the 20 XRP reserve and you already know how to deposit funds with GateHub and have done so, you can skip to “Step 3.” As long as you have a positive balance showing for your account, you will be able to continue.)*

GateHub offers two types of wallets:

1. GateHub hosted wallet
2. XRP wallet.

In my opinion, this is where a *major source of confusion* likely comes up when people start using GateHub and/or the XRPL DEX.   You can set up a GateHub hosted wallet for free, which will remain free to use, and there are no reserve requirements to enable a GateHub hosted wallet.

The hosted wallet will allow you to easily and quickly get funds deposited into the GateHub service and to purchase some XRP assets *(that can, afterward, be used to set up and activate an XRP wallet)*.

However, you also have the option to simply make a deposit directly into a newly created XRP wallet before it is even activated.  This option will result in an email being sent to you with instructions on how to proceed in order to activate the XRP wallet and set up any trust lines that may be necessary, based on the deposit you made.

I’ll outline both options, but I want to make one quick point:  I would exclusively use the XRP wallet after you are finished with this guide, regardless of which option you begin with.  The hosted wallet is centralized and not in your control - it could be hacked if GateHub is compromised.Also, the XRP wallet can interact directly with the XRPL DEX. So, it may be more effective to use the XRP wallet exclusively going forward *(For those interested, the differences between GateHub hosted and XRP wallets are discussed here:  [https://wallet.gatehub.net/#/help/faq](https://wallet.gatehub.net/#/help/faq); click on “Types of wallets”).*

**Option 1 - GateHub Hosted Wallet**

I will discuss the hosted wallet option first, while actually encouraging Option 2 be used instead.  You can read this and then move on to Option 2, jump immediately to option 2, or do both.

The goal here is to quickly finish Option 1 to get to setting up the XRP wallet next.  Let’s create the hosted wallet *(assuming it doesn’t already exist)*.  Go to "Wallet" on the menu located on the left side of the screen.  Click on the wallet drop-down menu in the upper-left corner of a screen *(check here to see if a hosted wallet already exists; if one does, you can skip to the deposit process, and, if not, then proceed)*.

[https://lh6.googleusercontent.com/YV3XOq3ijn5x2n43lmdas5en5rcdm2OWZypJAYfd4jPxRbT7RPnBXchclxlnZRYnqhtsEVZJXnrJWnQd46s-C6Txzi9VFmNQDxXS0FH5VmKgZzRXefu3b6CC6iIpkGlw4OE-jMaJ](https://lh6.googleusercontent.com/YV3XOq3ijn5x2n43lmdas5en5rcdm2OWZypJAYfd4jPxRbT7RPnBXchclxlnZRYnqhtsEVZJXnrJWnQd46s-C6Txzi9VFmNQDxXS0FH5VmKgZzRXefu3b6CC6iIpkGlw4OE-jMaJ)

Click "+Add Wallet".  Choose the “Hosted” wallet type.

[https://lh4.googleusercontent.com/yCUCUGTzTeLE_GjP-RkNKR6RFIgkyrV6Ho_x3xkj6gJMxSVm6cD1d2t_NwqCc1j_FQ7b_sNolBJZ48KNnU13598IwOad5VjEY2EVcbrb3W7bVyQj3HmlCyYnEfpf9wVtMLI4Eh3i](https://lh4.googleusercontent.com/yCUCUGTzTeLE_GjP-RkNKR6RFIgkyrV6Ho_x3xkj6gJMxSVm6cD1d2t_NwqCc1j_FQ7b_sNolBJZ48KNnU13598IwOad5VjEY2EVcbrb3W7bVyQj3HmlCyYnEfpf9wVtMLI4Eh3i)

If required, securely enter your account password.  Type in your wallet name *(this can be changed later)*.  Click “Create”.  The wallet is created, and should show up in the drop-down menu when you click on the top left wallet selector menu.

On the “Wallet” screen, make sure you have your hosted wallet selected in the top left corner.

[https://lh4.googleusercontent.com/cmGxp3dZ309xkANMssm1Cm2tsHI1KWNOiPjQhZY5KDvMX76pH7lfDocr9uJN87fpRVnaKtCVUMagyrMSrp9hr5ZSt46LpK6drPGjOOmWbFEmMu3pe5aRAYuqZY4xgOoGGhxPMful](https://lh4.googleusercontent.com/cmGxp3dZ309xkANMssm1Cm2tsHI1KWNOiPjQhZY5KDvMX76pH7lfDocr9uJN87fpRVnaKtCVUMagyrMSrp9hr5ZSt46LpK6drPGjOOmWbFEmMu3pe5aRAYuqZY4xgOoGGhxPMful)

Then, click on “+Add Funds” *(below the area showing which wallet you currently have selected)*.

[https://lh4.googleusercontent.com/GWnGjAx9-EynYBV0XzJlV7_sbvim5Rj_hQXXXl7XaH8UTj1NPt6F20a_8XVlo500PccfcXwaxqFOIc9ElbZfkcTxBDZ_JOEbl01CZYWgRIsKr_QxFg2zwTrJlFbnbdzqlzRafTtE](https://lh4.googleusercontent.com/GWnGjAx9-EynYBV0XzJlV7_sbvim5Rj_hQXXXl7XaH8UTj1NPt6F20a_8XVlo500PccfcXwaxqFOIc9ElbZfkcTxBDZ_JOEbl01CZYWgRIsKr_QxFg2zwTrJlFbnbdzqlzRafTtE)

Choose whichever type of currency you are going to deposit on the next screen, and, then, follow the instructions that they provide to you to make the transfer.  Once you initiate the transfer, you will need to wait on the deposit to clear and become available.  Return to the guide after.

[https://lh4.googleusercontent.com/rR9HOcCPxdOg0yAfAWmEuprx6ZHas-ECQUpo4yFzF6hgnPHQ3MMT7vxA2HJLFUY-x9FWzm8d551wt2fVUuwGaV3qKSpF8FC2kvY4X60q8pFc6mRlgQ92Ph58m_V-_sQay0MxooAL](https://lh4.googleusercontent.com/rR9HOcCPxdOg0yAfAWmEuprx6ZHas-ECQUpo4yFzF6hgnPHQ3MMT7vxA2HJLFUY-x9FWzm8d551wt2fVUuwGaV3qKSpF8FC2kvY4X60q8pFc6mRlgQ92Ph58m_V-_sQay0MxooAL)

This wallet also allows you access to simple, quick exchange of funds from one type to another at current exchange rate via GateHub’s private ledger for a small fee paid to GateHub *(to be clear, this is not the same as the XRPL DEX)*.  Once you have deposited funds into GateHub and they have cleared, click on “Exchange” *(left sidebar)*.

[https://lh3.googleusercontent.com/59XG---Oj01eum1WMmx4o_z6tv4UJYE9sJOlPSy1a0fsCOU4ndTuUQdrf9tNgU4_c6m0IwJIqzwnz6I7iinmmTOdSoPJiKJEpbu5O1Uk2kYfw2DM32wC7bqOc8Vu_Lb0JZDNFSRP](https://lh3.googleusercontent.com/59XG---Oj01eum1WMmx4o_z6tv4UJYE9sJOlPSy1a0fsCOU4ndTuUQdrf9tNgU4_c6m0IwJIqzwnz6I7iinmmTOdSoPJiKJEpbu5O1Uk2kYfw2DM32wC7bqOc8Vu_Lb0JZDNFSRP)

Ensure your hosted wallet is still selected in the top left corner of that screen.  In the main window *(center)*, you’ll want to make sure that you are exchanging whatever currency you deposited for whatever currency you want *(in this case, XRP)*, and the flow to do this on the screen you see is left to right.

[https://lh4.googleusercontent.com/xG3WC6XELMfTuQ1Y5rSgcunEvTuUSOkYWw6pUo1GOWHqE_gSM7yey_Ghf1d1aNXhCLbdt7g7pcXy4-WYCQHyM3AdCYZiZnDKrkV6fDXwrx699198hdR16tYgR-LWnnGo_W1v1Kjp](https://lh4.googleusercontent.com/xG3WC6XELMfTuQ1Y5rSgcunEvTuUSOkYWw6pUo1GOWHqE_gSM7yey_Ghf1d1aNXhCLbdt7g7pcXy4-WYCQHyM3AdCYZiZnDKrkV6fDXwrx699198hdR16tYgR-LWnnGo_W1v1Kjp)

What’s on the left will be “what you have,” and the right will be “what you want.”  If you have successfully deposited funds to GateHub and you have the proper wallet selected, those funds should automatically show up wherever you select that currency.	You will want to do this on the left side drop-down menu.  Next, select “XRP” in the right drop down menu.  Looking back at the left side, you will want to select how much of the funds you deposited to exchange for XRP.

[https://lh5.googleusercontent.com/R7b1HAyu6SplUWSspdlhOgPO7xtucki2D3aKT0KiUpMuXJjM60AEyRWzusqdWwg_HflN_tW8Noyn__h6XjXgksJRtgspBQgWHKw9R0ZhzvDiANmOolYRTjPMF_zdEtUL3WFtYCrs](https://lh5.googleusercontent.com/R7b1HAyu6SplUWSspdlhOgPO7xtucki2D3aKT0KiUpMuXJjM60AEyRWzusqdWwg_HflN_tW8Noyn__h6XjXgksJRtgspBQgWHKw9R0ZhzvDiANmOolYRTjPMF_zdEtUL3WFtYCrs)

I suggest clicking the “All Available” option to exchange the full amount.  As long as you are trying to exchange a relatively small amount of funds *(This amount will vary between users!)*, the liquidity provider for the exchange should have no issue settling the transaction.	Once you have completed these steps, click the “Exchange” button.  Smile - you are now the proud purchaser of XRP!  Notice I said purchaser, not owner.  It is deposited to that same hosted wallet.

Now, those XRP are available to transfer to the XRP wallet we are going to set up next. The point to be made, here, is that, as long as the assets are in your wallet, they’re yours; if they are in an exchange’s hosted wallet, they aren’t really yours yet even if they are currently credited to you.  The cryptocurrency community uses the phrase “Not your keys, not your crypto” to drive this point home.

Transferring this XRP to your own XRP wallet, that you control the secret key for,  cryptographically proves ownership of your assets.

Once again, to prepare to trade on the XRPL DEX, you must have an XRP wallet and associated secret key.  On the “Wallet” screen you see when you first log on (click “Wallet” in the left sidebar if you need to reach this screen), make sure you have the hosted GateHub wallet selected.	The balance should show you the new XRP amount you just received if you completed the previous steps.  Next, we need to add a new XRP wallet, assuming one doesn’t already exist.  To check, look in the area that displays the currently selected wallet in the top left; click on that drop down menu, and observe the wallets available.	You should, at minimum, see the hosted wallet there *(with your new XRP)*.  If you have an XRP wallet there already, that’s great - you can select it; if not, proceed with this: click “+Add Wallet'' -> Select “Create Wallet - XRP Ledger.”

[https://lh6.googleusercontent.com/wC-tIaMbH6uVsspXFrly4x1-WPqJ24w9JDsnws76FwAmDPFvdF2Uiw3LBNR-dR0mFnlF0YdgaGVrcu9KAIk5FLtwieOvs69LFRFy-VEZQslCZtlz349PsvV7PIYzeLfUYBWrjzVS](https://lh6.googleusercontent.com/wC-tIaMbH6uVsspXFrly4x1-WPqJ24w9JDsnws76FwAmDPFvdF2Uiw3LBNR-dR0mFnlF0YdgaGVrcu9KAIk5FLtwieOvs69LFRFy-VEZQslCZtlz349PsvV7PIYzeLfUYBWrjzVS)

Once the wallet is created, if it is not already selected, then do so.

[https://lh5.googleusercontent.com/l2BzidibHZIv5_uRFDdUaY-mKFGzRwLS_NXy2_oZqgaqPgrV6RKVxy1-3c9rT9u_ByF0n-bp16AqWwjJqfm3IY8PVPeNVbZr4CRM7ocreqzuENKnp7_59V2jLbaX1hrneMm6Oxtn](https://lh5.googleusercontent.com/l2BzidibHZIv5_uRFDdUaY-mKFGzRwLS_NXy2_oZqgaqPgrV6RKVxy1-3c9rT9u_ByF0n-bp16AqWwjJqfm3IY8PVPeNVbZr4CRM7ocreqzuENKnp7_59V2jLbaX1hrneMm6Oxtn)

Right now, this XRP wallet is created but inactive, because it does not yet have a reserve of 20 XRP balance met.  Now, we want to transfer those XRP funds we just obtained from the Hosted wallet to the XRP wallet.  In order to do so, we need to know this XRP wallet’s XRP public address.  Select the XRP wallet, and look at the new screen.  In the main screen area *(middle)*, you should see a place where the address is listed and a button you can click to copy the public address easily.

[https://lh5.googleusercontent.com/gQsVPtzx9VIMkMGs6UR6PnUPEnJIUoVqFt91SB6GqT4NXRIKDJ8E2K_2INfQ58bSLpYWI06eJ9qGf5Tre6i6qdaWluc9zZ-j-Svy5LfScybkR8HtOmnfD-cTKq4H5GbspL2YrjJC](https://lh5.googleusercontent.com/gQsVPtzx9VIMkMGs6UR6PnUPEnJIUoVqFt91SB6GqT4NXRIKDJ8E2K_2INfQ58bSLpYWI06eJ9qGf5Tre6i6qdaWluc9zZ-j-Svy5LfScybkR8HtOmnfD-cTKq4H5GbspL2YrjJC)

Now, we need to go back to the hosted wallet in order to initiate the transfer; go to the top left of the screen, click the wallet selection drop-down menu, and select the GateHub hosted wallet with the non-zero XRP balance.

[https://lh3.googleusercontent.com/0K_9GPqBfHrW64kvjwb4rV2bc25LZrczt5GmWsiTWyUki5YE-PA02P19lGtg756DQoC20U-azJYf1qQ9GryuYlQFJK7EFr8xGIDa_kn2S_6t77MD3YyADOFzkOeVzU537D9hfdtQ](https://lh3.googleusercontent.com/0K_9GPqBfHrW64kvjwb4rV2bc25LZrczt5GmWsiTWyUki5YE-PA02P19lGtg756DQoC20U-azJYf1qQ9GryuYlQFJK7EFr8xGIDa_kn2S_6t77MD3YyADOFzkOeVzU537D9hfdtQ)

Click "Send Payment."

[https://lh5.googleusercontent.com/EhOdFVuvcMDu-iGr--lE1drZdDtjYQbKqEzUwnjoZLSSIueMu2g6Lb7bMMr1PA9VuDu0wSZE0FVaXFXHtASWt99FSxG-OrHOGuHnGEZysecyoH9S3uoKWDtbLXomm8QRxKu6Mjjp](https://lh5.googleusercontent.com/EhOdFVuvcMDu-iGr--lE1drZdDtjYQbKqEzUwnjoZLSSIueMu2g6Lb7bMMr1PA9VuDu0wSZE0FVaXFXHtASWt99FSxG-OrHOGuHnGEZysecyoH9S3uoKWDtbLXomm8QRxKu6Mjjp)

Select the currency you wish to send.

[https://lh6.googleusercontent.com/2BlW7e3svy4EvJIqNHtxO1QfNrXjDwcstSn9Fx3DScdpaeHjQrv7kKBUEOQtNMlgwwNsiES6C2jQdhimitVvLzF3gP5k-kY0vqVbHcVAyAFROo-ndm8hW-rPe_85Oe5H0MiEkZb0](https://lh6.googleusercontent.com/2BlW7e3svy4EvJIqNHtxO1QfNrXjDwcstSn9Fx3DScdpaeHjQrv7kKBUEOQtNMlgwwNsiES6C2jQdhimitVvLzF3gP5k-kY0vqVbHcVAyAFROo-ndm8hW-rPe_85Oe5H0MiEkZb0)

Enter the receiver address by pasting the address you copied earlier.  Enter the amount you wish to send (perhaps the full amount, here, would be best, since this is the wallet we intend to use in the future, disregarding the hosted wallet).

[https://lh3.googleusercontent.com/rq1JHYlwgfPJBrbWoInx_XxFG2ANiV8gDe0W8zsM0Re5US0xTAZ7XxcElS8e-akCzw9gJ9IqVJi6jgYBHoKjvKQ-u3BXFZRkDQ0GyjSHqqtLI8XS_yV6hA9N5diRdpUvtLPo6fLK](https://lh3.googleusercontent.com/rq1JHYlwgfPJBrbWoInx_XxFG2ANiV8gDe0W8zsM0Re5US0xTAZ7XxcElS8e-akCzw9gJ9IqVJi6jgYBHoKjvKQ-u3BXFZRkDQ0GyjSHqqtLI8XS_yV6hA9N5diRdpUvtLPo6fLK)

Click "Continue."  As soon as the XRP is transferred to the XRP wallet and as long as the amount of XRP you are transferring is 20 or greater, when the balance hits that wallet, it will automatically create the 20 XRP reserve when the transaction processes; you don’t need to do anything else except make the transfer happen in order to set the 20 XRP reserve and activate the wallet.	Smile, again - you now the proud owner XRP - it’s “your keys, your crypto!”  We’re very close to being done, now.  Once that XRP wallet is created, you should make it a habit to transact with it, not the hosted wallet.  The hosted wallet, though, can be used as an ILP payment pointer, if you want (another guide for another day perhaps!).

**Option 2 - XRP Wallet**

*(GateHub also allows you to import an XRP wallet you already created elsewhere by passing them the Secret Key, such as one you create on XUMM.)*

***WARNING, SECRET KEYS SHOULD BE HANDLED WITH EXTREME CAUTION!***

***Users should consider creating a new Regular Key pair for interacting with web services.***

Let’s create the XRP wallet *(assuming it doesn’t already exist)*.  Go to "Wallet" on the menu located on the left side of the screen.

[https://lh4.googleusercontent.com/gwTVojZaYhKP5pyUDVbUxHhHoBg4zH5EfZsuS0SyiAR9kTJPTS37M80CvUKvdqqEvO90IkvBaohP77xEFu9ZJmA-Qh77Bzul8Y9gIqmFSQdUvCRHSBXRGdCHh0qITydBHlyYAAwJ](https://lh4.googleusercontent.com/gwTVojZaYhKP5pyUDVbUxHhHoBg4zH5EfZsuS0SyiAR9kTJPTS37M80CvUKvdqqEvO90IkvBaohP77xEFu9ZJmA-Qh77Bzul8Y9gIqmFSQdUvCRHSBXRGdCHh0qITydBHlyYAAwJ)

Click on the wallet drop-down menu in the upper-left corner of a screen *(check here to see if a hosted wallet already exists; if one does, you can skip to the deposit process, and, if not, then proceed)*.	Click "+Add Wallet".

[https://lh5.googleusercontent.com/_ChWs6D-uJT1qJzB296iuZmmldbsDu-NoewAvFnUQYaQDQ3s3ISp7rM89gYGn_3UcE7Gh1idVfbygK0xLOZUPS0ybrrp_axLxDOS7fSWtuLhN5e0SrJdMMgYNaLYax5765BBOOpR](https://lh5.googleusercontent.com/_ChWs6D-uJT1qJzB296iuZmmldbsDu-NoewAvFnUQYaQDQ3s3ISp7rM89gYGn_3UcE7Gh1idVfbygK0xLOZUPS0ybrrp_axLxDOS7fSWtuLhN5e0SrJdMMgYNaLYax5765BBOOpR)

Choose the “XRP” wallet type.  If required, enter your account password.  Type in your wallet name *(can be changed later)*.

[https://lh5.googleusercontent.com/znAj8Zkj2tgaOH3W6iYhTI59GdAGuBV-AENj2w5MIA3dACcG4HzEk5vFnzoBh4Us-eE3fa1v5_XQx8CUvnBqNkyTpjB2IYyUJ6emBgohPRfuSwmbgw1fD1EHIi-0CcjS88bRZgnL](https://lh5.googleusercontent.com/znAj8Zkj2tgaOH3W6iYhTI59GdAGuBV-AENj2w5MIA3dACcG4HzEk5vFnzoBh4Us-eE3fa1v5_XQx8CUvnBqNkyTpjB2IYyUJ6emBgohPRfuSwmbgw1fD1EHIi-0CcjS88bRZgnL)

`Click “Create”.  The wallet is created, and should show up in the drop-down menu when you click on the top left wallet selector menu.

[https://lh5.googleusercontent.com/dSkYPByiCTVtW1qua16aDxMIkLepT_NqStKqu2ZfW6QSYlLUadvdgb-drhbx1IRx3hU8w1R-0Bs-OMLSdNbT0ytaGFj1b0HGzKyGWwX6Fp99aPlpsiWkSfVtBZTW1fXmMHu1HgH6](https://lh5.googleusercontent.com/dSkYPByiCTVtW1qua16aDxMIkLepT_NqStKqu2ZfW6QSYlLUadvdgb-drhbx1IRx3hU8w1R-0Bs-OMLSdNbT0ytaGFj1b0HGzKyGWwX6Fp99aPlpsiWkSfVtBZTW1fXmMHu1HgH6)

On the “Wallet” screen, make sure you have your XRP wallet selected in the top left corner.  Then, click on “+Add Funds” *(below the area showing which wallet you currently have selected)*.

[https://lh6.googleusercontent.com/cf7QSF9hGoiQKap2b3zMNVusuaGVuLfYQvSyjEJz4E-DLws2vNx-LJlQ27hThL07NUQ_XbGZzv6pwRLuLBjZuJp7AYmZRto5fWihJh3EVueUhetbZi3-VzEx7oOv2sEOT9KL1RlT](https://lh6.googleusercontent.com/cf7QSF9hGoiQKap2b3zMNVusuaGVuLfYQvSyjEJz4E-DLws2vNx-LJlQ27hThL07NUQ_XbGZzv6pwRLuLBjZuJp7AYmZRto5fWihJh3EVueUhetbZi3-VzEx7oOv2sEOT9KL1RlT)

Choose whichever type of currency you are going to deposit on the next screen, and, then, follow the instructions that they provide to you to make the transfer.

[https://lh3.googleusercontent.com/gYnYmvZvU7FL9CvyeaeT_Lq3trn0ByB8YW90SbxS1UVeV_b0RKDoH9ZV0DjSqYwHMGJ2eUuzwrsxQ7_9_oCigLfWvJt6v5ggMf-8Lo5ODBxoT_qwhoidYIGpRv8Z6sM0ecfECrME](https://lh3.googleusercontent.com/gYnYmvZvU7FL9CvyeaeT_Lq3trn0ByB8YW90SbxS1UVeV_b0RKDoH9ZV0DjSqYwHMGJ2eUuzwrsxQ7_9_oCigLfWvJt6v5ggMf-8Lo5ODBxoT_qwhoidYIGpRv8Z6sM0ecfECrME)

Once you initiate the transfer, you will need to wait on the deposit to clear and become available.  Return to this guide after.

***Author’s Note:** I want to discuss one point that I hope clears any confusion others may have that was similar to my own, which prevented me from ever using GateHub previously.  I wasn’t willing to put real funds at risk to try to determine which of my speculations was the truth.	If you deposit funds via bank wire/SEPA transfer or via cryptocurrency transfer with GateHub into an XRP Wallet:  they will automatically hold those transferred assets in reserve (in their own appropriate wallet for that native asset) and credit your XRP wallet with the appropriate amount of corresponding digital asset IOU on the XRPL, unless, of course, you are transferring XRP to them, in which case the native XRP is put in your wallet.  You will not need to tell them to do the issuance step, as you, in a way, already did so by initiating the transfer to them via the XRP Wallet (instead of a hosted wallet).  As long as you already have the appropriate trust lines set up for that XRP wallet, your wallet will be credited with the appropriate IOUs representing those funds.	If you don’t have the appropriate trust lines set up, then you can do so either before or after you initiate the transfer (Customer support explains that they will send you an email with instructions).  A side take:  you may want to just get the trust lines set before you transfer the funds.  That would require already having XRP you can transfer to the wallet to provide the necessary XRP to set the trust lines.  Bitstamp might be a good option for this, since you should want to set up an account with them, regardless, so that you can make use of that Gateway, too.  You can also just use the hosted GateHub wallet, too, if this is your preference.*

**Step 3 -  Question: *Have you set up the appropriate trust line(s) between your XRP wallet and the wallet of the Gateway provider for each type of funds you plan to deposit with them?***

First, a quick aside about trust lines.  If you recall, the XRPL DEX allows you to trade two things:  XRP and issued currencies.  In order for your wallet to be able to hold and trade the issued currencies, you need to set up a trust line between your XRP wallet and the issuers XRP wallet for each type of issuance you want to interact with *(such as USD-IOU, EUR-IOU, BTC-IOU, etc.)*.Also, keep in mind that each Gateway *(GateHub, Bitstamp, etc.)* issues its own IOUs for any asset, so you will need to establish a new trust line for each Gateway’s USD-IOU, EUR-IOU, etc.  In this case, we are working with GateHub’s Gateway providers.  If you wanted to take on IOUs issued by the Bitstamp Gateway provider and you already have trust lines set for GateHub’s Gateway providers, you would need additional trust lines *(to beat the dead horse - yes, even if you already have one GateHub USD-IOU trust line, you would need a Bitstamp USD-IOU trust line, too)*.Each trust line you establish costs 5 XRP that are added to your initial 20 XRP reserve *(just like the initial reserve, you can recover any trust line reserve you set up by, later, zeroing the balance of that asset from your wallet and cancelling the trust line; those 5 XRP will be released and available to you once again)*.

To set a trust line for your XRP wallet for a type of IOU asset, do the following:  Go to "Wallet" -> Select the wallet from a blue drop-down menu at the top left -> Click "Advanced" -> Under "XRPL Setting" click "TRUST LINES"

[https://lh3.googleusercontent.com/ybyM6p3HM72zhJA87-hONLQC-cphNzbUGUN1gsQ1FGdk5qiriVUlqWj7l_9QDAHmZuy6f-5O03uokfqT_5FHfuYgXUjn8xoU6vrkX4PkXDyPSYWKQnOwhr2Ebl2mlWfWfCuCaSVP](https://lh3.googleusercontent.com/ybyM6p3HM72zhJA87-hONLQC-cphNzbUGUN1gsQ1FGdk5qiriVUlqWj7l_9QDAHmZuy6f-5O03uokfqT_5FHfuYgXUjn8xoU6vrkX4PkXDyPSYWKQnOwhr2Ebl2mlWfWfCuCaSVP)

- > Look for your required currency

[https://lh3.googleusercontent.com/IkValopcJjlCx_fvJ-zVLn_h9igCQaGqWoNF3QOJQJgkeu9qPsg5BiyxaHv4LrLu1N6QeI3QYuow-PINpBL1wsNcolfpHSQgn3zb2pCZW-lcfhJ-4NttfSsnZriO7v4OxDvDOGDg](https://lh3.googleusercontent.com/IkValopcJjlCx_fvJ-zVLn_h9igCQaGqWoNF3QOJQJgkeu9qPsg5BiyxaHv4LrLu1N6QeI3QYuow-PINpBL1wsNcolfpHSQgn3zb2pCZW-lcfhJ-4NttfSsnZriO7v4OxDvDOGDg)

- > Click "Enable" and "Confirm". *(In GateHub’s website, you may have to establish an active connection [discussed earlier] to a particular Gateway within Gatehub in order to make the option available to set a trust line for the assets they provide).*To check that your trust lines were appropriately set, you can do the following: Go to "Wallet" -> Select the wallet from a blue drop-down menu at the top left -> Click "Advanced" -> Under "XRPL Settings" observe the "TRUST LINES" display. Does the number of Trust lines equal more than 0? Then, you have successfully established trust lines for your XRP wallet.

As of this moment, you are now completely set to trade on the XRPL DEX with this XRP wallet that you established with GateHub.  Congratulations!You have two options now to interact with the DEX.  You can either use the GateHub interface in order to interact with the XRPL DEX *(Go to “Trade” in the left sidebar)*:

[https://lh4.googleusercontent.com/QVfI8ZEcHJ4CGk-nrx7occz2GP3u1GHgd0zQW6ksiyj5QQr6NQKpfQI385Ap_YWRaFvpb5Xga99PFuQ_Z0G2jDKEN5MjZVNWlr2C_sGwol3ul7syaiU8M0BxvuJPJSoIHbvJ45wn](https://lh4.googleusercontent.com/QVfI8ZEcHJ4CGk-nrx7occz2GP3u1GHgd0zQW6ksiyj5QQr6NQKpfQI385Ap_YWRaFvpb5Xga99PFuQ_Z0G2jDKEN5MjZVNWlr2C_sGwol3ul7syaiU8M0BxvuJPJSoIHbvJ45wn)

[[  The remainder of this page is intentionally left blank. Continue on to the next page.  ]]

[https://lh3.googleusercontent.com/arE5Ox1jwiGMh7FkgH9SmWOcQbFEYu3gd9RYcNDBv6CgosWy4oXIFL_fk_pksWHekVXNKbOJ10qZ-HCbBPJuZmGHglvEyADa2I9jD0j_Hfu5uXzGFhjtfJIx1MugFB3C0mPDm1Xc](https://lh3.googleusercontent.com/arE5Ox1jwiGMh7FkgH9SmWOcQbFEYu3gd9RYcNDBv6CgosWy4oXIFL_fk_pksWHekVXNKbOJ10qZ-HCbBPJuZmGHglvEyADa2I9jD0j_Hfu5uXzGFhjtfJIx1MugFB3C0mPDm1Xc)

You can import this same XRP wallet into XUMM, followed by integration with the XRP Toolkit *(discussed in pathway #1)*.  You have the secret key for this wallet, so that is an entirely possible option.

***WARNING, SECRET KEYS SHOULD BE HANDLED WITH EXTREME CAUTION!***

***Users should consider creating a new Regular Key pair for interacting with web services.***

The mechanics of how to set custom trust lines are also covered in other guides available on both GateHub and XRP Toolkit.

If you have any other questions regarding how to use GateHub to get the trust lines set up in order to use the DEX or to get the IOUs of the assets you are depositing with GateHub into your XRP wallet, I absolutely suggest you read the GateHub Support Documentation provided here:  [https://support.gatehub.net/hc/en-us/articles/360021318533](https://support.gatehub.net/hc/en-us/articles/360021318533-Register-a-GateHub-Account).  You can sift through the different topics on the left sidebar and find answers to questions you have.

*(You can actually still use the XRP Toolkit to access XRPL DEX trading even if you use GateHub to create your XRP wallet!  In other words, it is available to you, regardless of which pathway you go through to make an XRP wallet.  You would simply import your XRP wallet made with GateHub into XUMM, so that it is available in XRP Toolkit.  That fact should actually encourage you to follow pathway #1 as well, even if you don’t set up a separate XRP wallet for that service).*

## **Conclusions**

Now that you’ve made it through this guide, you should feel a great sense of pride.  You have learned one of the critically important tools of the XRP ecosystem, and that power is now yours.Now that you have this power, I encourage you to stop buying XRP from the centralized exchanges.  Many may wonder why I say that.  Consider the following:  if you commit to this strategy for acquiring XRP, instead of participating in centralized exchanges, and later make your trades using the XRPL DEX, you will become a direct contributor to the XRP ecosystem helping it to grow more robust and liquid!You, knowingly or unknowingly, will become a direct contributor in the liquidity provisioning of the XRP markets.  This is important because, as that happens, it will be more difficult for centralized exchanges to manipulate the value of XRP with various *strategies*.  If you participate in centralized exchanges, you are at their ‘market making mercy’.  Their platform machinations are more valuable than your assets, and on their centralized platforms, only they are the direct contributors to their value -- unless you can transparently track your assets by transaction IDs, the exchanges are going to use the value of your assets *for* themselves, even if you think they are static and secure.The XRP market is less liquid due to ongoing action; but that doesn’t mean there is nothing we can do.  If you participate in the XRPL DEX, you contribute to the overall strength of the entire XRP ecosystem, because you are now a direct contributor in it, just like them.  The market becomes more liquid and individual agents reclaim their ownership of their own assets.  Again, you should feel an incredible sense of strength and pride knowing you have this power.  All you have to do is seize it for yourself.  Make these techniques your habit.  In time, with all of us doing the same, we will see the destination we are all hoping for.

You are what you have been waiting for.

“Aller anfang ist schwer. Anfang ist anfang….”

*Take care, be well, and be good to each other!*

## **Postscript:**

This content was produced for educational purposes and should remain free from charge.  If you found any personal value in the educational use of this report, please consider supporting the author and editor by questioning, commenting, or even testing the guide with a small deposit of XRP to the author’s address listed on the title page .  You too can contribute towards continued independent XRPL education by exploring this exciting technology with the rest of the world.