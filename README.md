# Lawmert Cart

## Overview

Lawmert, seller of fine goods, has hired _YOU_ to fix up their cart application. This means fixing the business logic errors and implementing the new features as required.

Required features:

 * Customer should be able to add item to cart by clicking a product.
 * Customer should be able to remove item from cart by clicking a remove button.
 * Customer should be able to adjust quantity of item in cart.
 * Customer should be able to view their total purchase amount.
 * Customer should be able to clear all items from cart by clicking a button.
 * Customer should see "Your cart is empty" when no items are in the cart.

Here is what such a thing should look like according to UX:

![full cart](http://i.imgur.com/IWIoGvh.png)

![empty cart](http://i.imgur.com/3VqMdkZ.png)

Unfortunately here's what it currently looks like:

![existing](http://i.imgur.com/7DSC569.png)

There are some sensible invariants:

 * Customer should not be able to have item of quantity 0 or less in their cart.
 * Customer should only see one of a given item in their cart.

There are some sensible developer best practices:

 * Your code should pass any test functionality of `npm test`.
 * Your result should match the UX.

Things which you do NOT need to touch (but can if you want to):

 * `config/*` - setup files for webpack and friends.
 * `entry/*` - entrypoint to the application.
 * `public/*` - static prebuilt assets (i.e. the main HTML file).

Although not _required_, feel free to:

 * Use external libraries.
 * Refactor existing code.
 * Alter the user interface.

If you do these things it should be noted that you explain _why_ you're doing them. For example, if you alter the UI and decide consciously not to use icons explain your reasoning.

## Submission Process

Your submission should be a series of git commits. You're free to commit things however you like. You should mention what you're changing and why you're changing it, however.

If there are things you'd like to change but don't know how to or don't have time to, feel free to mark them with a `TODO` so we know you've thought about them.

If there are broader architecture designs you'd like to discuss, feel free to add a markdown document in the project root called `NOTES.md` or similar.

Once you're done, simply collect everything:

```sh
tar -zcvf my-code.tar.gz .git
```

And then send it back.

## Setup

Getting going is easy!

```sh
npm install
npm run dev
open http://localhost:8080/
```

Notes to changes for the required features, issues and invariants:
0. All the described required features, issues and invariants have been implemented and solved.

1. package.json: Using npm version 5.6.0 to run the command 'npm run dev' would generate some dependency errors for:
   babel-core and json5, so have to install and include these two modules to get it run on local.

2. public/ folder, to add the images for the cart, product, plus/minus and recycle bin.

3. /component/cart.js, to refactor for the UI changes including the image loading and style sheets;
   add clean all items action and delete one item action; add an inline style sheet (ttStyle: name in code) for
   the grand total table cell; apply toFixed(2) function for the total numbers to be 2 decimals.

4. /component/products.js, to add image on the left of the title.

5. /reducer/cart.js, to refactor the logic to only see one of given item in the cart(add item action);
   and disallow negative items in cart(setQuantity action).

6. /component/styles.css, style definition for the layout.

7. 'npm test' has been run with problems being fixed.

8. The zip file does not contain the node_modules directory, to run please run 'npm install' after unzip and
   use the same running steps. also available repo url: https://github.com/untaylor/my-cart-code

9. Not sure if changes can be committed through git. tried to locate the .git file in the root directory and found
   no such directory and that the original zip file may not be exported from git archive.
   Running 'git log' does not show any commit history either.
   Thanks!
