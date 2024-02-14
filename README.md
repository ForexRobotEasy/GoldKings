# GoldKings Expert Advisor

This expert advisor, named GoldKings, is a forex trading robot that utilizes a grid rollback trading system. It is developed by the Forex Robot Easy Team and more information about the product can be found on their website [here](https://forexroboteasy.com/forex-robot-review/goldkings-forex-software-review-grid-rollback-trading-system/). Please note that ForexRobotEasy is not the official developer of this product, but is only providing a sample code that can work as described in the product.

## Strategy Overview

The GoldKings expert advisor uses a combination of technical indicators such as RSI (Relative Strength Index), Bollinger Bands, and Stochastic to identify trading opportunities in the market. It implements a grid trading strategy, where positions are opened at specific price levels and managed based on certain conditions.

## Input Parameters

The expert advisor provides several input parameters that can be customized according to individual trading preferences. These parameters include:

- **LotSize**: The initial lot size for opening positions. Default value is 0.01.
- **TakeProfit**: The take profit level for closing positions. Default value is 100.0.
- **GridStep**: The grid step size for opening new positions. Default value is 20.0.
- **MaxPositions**: The maximum number of positions that can be opened. Default value is 5.
- **CloseOnTotalProfit**: An option to close positions based on the total profit. Default value is true.

## Indicator Variables

The expert advisor uses the following indicator variables:

- **rsiHandle**: Stores the handle for the RSI indicator.
- **bbHandle**: Stores the handle for the Bollinger Bands indicator.
- **dsHandle**: Stores the handle for the Stochastic indicator.

## Position Management Variables

The expert advisor maintains the following position management variables:

- **totalPositions**: Keeps track of the total number of open positions.
- **totalProfit**: Stores the total profit made from closed positions.

## Custom Indicator Initialization Function

The `OnInit()` function is responsible for initializing the custom indicators used by the expert advisor. It sets up the handles for the RSI, Bollinger Bands, and Stochastic indicators.

## Custom Expert Advisor Start Function

The `OnStart()` function is the main entry point for the expert advisor. It loops through all bars in the chart and performs the following actions:

1. Calculates the values of the indicators (RSI, Bollinger Bands, and Stochastic) for each bar.
2. Checks if the RSI value is above 70 and the option to close positions on total profit is enabled. If true, it closes all positions and calculates the total profit.
3. Checks if the price is below the lower Bollinger Band, the option to close positions on total profit is enabled, and the total profit is above 1000.0. If true, it closes all positions and resets the total profit.
4. Checks if there are no open positions, the total profit is below -1000.0, and opens a new position.
5. Checks if there are open positions, the total profit is below -1000.0, and hedges the existing positions.

Lastly, it closes any remaining positions.

## Function to Open a New Position

The `OpenPosition()` function is called when a new position needs to be opened. It sends a buy order at the current market price and increases the total positions count if the order is executed successfully.

## Function to Close All Positions

The `ClosePositions()` function is responsible for closing all open positions. It loops through all open orders, selects each order, closes it, and calculates the profit made from the closed order. It also decreases the total positions count accordingly.

## Function to Hedge Existing Positions

The `HedgePositions()` function is used to hedge the existing positions. It loops through all open orders, selects each order, sends a sell order at the current market price to hedge the position, and adjusts the total positions count accordingly.

Please note that this is a simplified overview of the GoldKings expert advisor's functionality. For a more detailed understanding and trading results of this product, it is recommended to visit the official developer's website using the provided link [here](https://forexroboteasy.com/forex-robot-review/goldkings-forex-software-review-grid-rollback-trading-system/).
