Coin Flip
=========

Coin Flip is a game where the player tries to guess the outcome of a coin flip. It is one of the simplest contracts implementing random numbers.

![img](https://docs.near.org/assets/images/coin-flip-54eec9769bd7c2c68778790d69fcd4ab.png)

* * *

Starting the Game[​](#starting-the-game "Direct link to heading")
-----------------------------------------------------------------

You have two options to start the example:

1.  **Recommended:** use the app through Gitpod (a web-based interactive environment)
2.  Clone the project locally .

*   🌐 JavaScript

Gitpod

Clone locally

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/coin-flip-js.git)

🌐 `https://github.com/near-examples/coin-flip-js.git`

If you choose Gitpod, a new browser window will open automatically with the code. Give it a minute, and the front-end will pop up (ensure the pop-up window is not blocked).

If you are running the app locally, enter the directory where you cloned it and use `yarn` to install dependencies, and `yarn start` to start it.

    cd counteryarnyarn deployyarn start

Your contract will then be **compiled** and **deployed** to an **account** in the `testnet` network. When done, a browser window should open.

* * *

Interacting With the Counter[​](#interacting-with-the-counter "Direct link to heading")
---------------------------------------------------------------------------------------

Go ahead and log in with your NEAR account. If you don't have one, you can create one on the fly. Once logged in, use the `tails` and `heads` buttons to try to guess the next coin flip outcome.

![img](https://docs.near.org/assets/images/coin-flip-54eec9769bd7c2c68778790d69fcd4ab.png) _Frontend of the Game_

* * *

Structure of a dApp[​](#structure-of-a-dapp "Direct link to heading")
---------------------------------------------------------------------

Now that you understand what the dApp does, let us take a closer look to its structure:

1.  The frontend code lives in the `/frontend` folder.
2.  The smart contract code is in the `/contract` folder.

### Contract[​](#contract "Direct link to heading")

The contract presents 2 methods: `flip_coin`, and `points_of`.

*   🌐 JavaScript

contract/src/contract.ts

    loading...

[See full example on GitHub](https://github.com/near-examples/coin-flip-workshop-js/blob/main/contract/src/contract.ts#L23-L56#)

### Frontend[​](#frontend "Direct link to heading")

The frontend is composed by a single HTML file (`/index.html`). This file defines the components displayed in the screen.

The website's logic lives in `/assets/js/index.js`, which communicates with the contract through a `wallet`. You will notice in `/assets/js/index.js` the following code:

*   🌐 JavaScript

frontend/index.js

    loading...

[See full example on GitHub](https://github.com/near-examples/coin-flip-workshop-js/blob/main/frontend/index.js#L10-L19#)

It indicates our app, when it starts, to check if the user is already logged in and execute either `signedInFlow()` or `signedOutFlow()`.

* * *

Testing[​](#testing "Direct link to heading")
---------------------------------------------

When writing smart contracts, it is very important to test all methods exhaustively. In this project, you have two types: unit and integration tests. Before digging into them, go ahead and perform the tests present in the dApp through the command `yarn test`.

### Integration test[​](#integration-test "Direct link to heading")

Integration tests are generally written in JavaScript. They automatically deploy a new contract and execute methods on it. In this way, integration tests simulate interactions from users in a realistic scenario. You will find the integration tests for the `counter` in `tests/integration-tests`.

*   🌐 JavaScript

integration-tests/src/main.ava.ts

    loading...

[See full example on GitHub](https://github.com/near-examples/coin-flip-workshop-js/blob/main/integration-tests/src/main.ava.ts#L32-L56#)

* * *

A Note On Randomness[​](#a-note-on-randomness "Direct link to heading")
-----------------------------------------------------------------------

Randomness in the blockchain is a complex subject. We recommend you to read and investigate about it. You can start with our [security page on it](/develop/contracts/security/random).
