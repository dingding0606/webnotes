1.  Create a template; if the user visit the page via GET, render the template. Elif POST, transfer share and symbol back to application.py

2.  Check:

3.  1.  Symbol is valid or not

    2.  1.  Valid: store the data (price)
        2.  Invalid: apology()

    3.  Enough money or not: SELECT cash FROM users WHERE id = 1

    4.  1.  Get the current money from db using execute

        2.  Compare money with price * shares

        3.  1.  If yes: go to step 3
            2.  If no: render apology()

    5.  INSERT INTO history (userid, symbol, price, shares, time)

    6.  UPDATE users SET cash = cash - 50 WHERE id=1

    7.  [Confirmation]

    8.  Render to history page



history.db

| userid (id) | symbol | price | shares  | time     | index                         |
| ----------- | ------ | ----- | ------- | -------- | ----------------------------- |
| INTEGER     | TEXT   | REAL  | INTEGER | DATETIME | INTEGER, PRIMARY, INCREMENTAL |







### index

| stocks owned | shares | current price | total value of each holding |
| ------------ | ------ | ------------- | --------------------------- |
|              |        |               |                             |

Balance

Current value: Balance + total value

1.  Html page
2.  get 

`SELECT symbol, sum(shares) FROM history GROUP BY symbol`



###sell

1.  a select list of symbol
2.  input shares
3.  POST
4.  Check if input is valid:
    1.  Not valid: apology
    2.  Valid:
        1.  check current price
            1.  if can not check: apology
            2.  Else:
                1.  `UPDATE users SET cash = cash + :money_sold WHERE id=:id`
                2.  `INSERT INTO history (userid, symbol, price, shares) VALUES(:id, :symbol, :price, :shares)`: note that shares will be negative
5.  Render to "/"



### history

1.  get everything from data base
2.  chagne the order 
3.  render everything on html page