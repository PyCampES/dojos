# Coins

Implement a code for a coin changer calculator, so given an amount, and a set of coins, it will return the quantity of each coin required to give that amount.

## Proposed iterations

### Basic coin changer
In this iteration, the coin changer will:

* receive an amount of money
* be provided with a predefined set of coins, with the following classes: 5, 10, 20, and 50 cents, and 1, and 2 euros.

For this iteration, the following rules are to be followed:

* The amount will always be multiple of 5 cents, as a float number with two decimal positions.
* The system will have coins enough of each class.
*There's no limit on the quantity and class of coins used.

For instance, let's say the amount is 25 cents, so the program could work like this:
```
python coins.py 0.25
5 x 5c
```

Other possible amounts would be like the following:
```
python coins.py 2.35
47 x 5c
python coins.py 3.00
60 x 5c
python coins.py 5.50
110 x 5c
```

So, for this first iteration, the easiest path would be to provide only 5c coins.

This iteration result is intended to be simple and neat, without too much complications. The expected time to complete this iteration is 15 to 20 minutes.

### Optimal coin changer
In this iteration, the result should be the optimal according to the quantity of coins it provides, so the classes should be used in such a way, that the total number of coins is the lesser possible.

For the same amounts of the previous iteration examples, we should get:
```
python coins.py 0.25
1 x 20c, 1 x 5c, total 2 coins
python coins.py 2.35
1 x 2e, 1 x 20c, 1 x 10c, 1 x 5c, total 4 coins
python coins.py 3.00
1 x 2e, 1 x 1e, total 2 coins
python coins.py 5.50
2 x 2e, 1 x 1e, 1 x 50c total 4 coins
```

### Optimal limited coin changer
For this iteration, also the quantity of coins of each class is limited, so the program will be limited to have the following quantities:
```
5 cents: 2 coins
10 cents: 2 coins
20 cents: 2 coins
50 cents: 2 coins
1 euro: 2 coins
2 euro: 1 coin
```

For this iteration, there will be no amount which will require more coins than these.

For the examples followed so far, the results should be:
```
python coins.py 0.25
1 x 20c, 1 x 5c, total 2 coins
python coins.py 2.35
1 x 2e, 1 x 20c, 1 x 10c, 1 x 5c, total 4 coins
python coins.py 3.00
1 x 2e, 1 x 1e, total 2 coins
python coins.py 5.50
1 x 2e, 2 x 1e, 2 x 50c, 2 x 20c, 1 x 10c, total 8 coins
```

### Currency defined optimal limited changer
In this iteration, the code will be extended to allow the changer to have defined the currency, let's say EURO and USD. For the US currency, the classes will be 5, 10, 25 and 5c cents, and 1 dollar. The coin quantity to be used is still expected to be optimal, and the possibility of having a limited set of coins is also to be considered.
