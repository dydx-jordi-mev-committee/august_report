This is a simple repository containing two folders:

- Liquidation blocks
- Non liquidation blocks

Inside each folder, we've uploaded a set of JSON files corresponding to the logs by the MEV Committee node, where we see the block proposer matches and the ones expected by our validator, as well as the liquidations and block prices for each asset.

Additionally, we share a few queries used for querying Numia data useful for each analysis. On top of that, the committee has also created the following simple streamlit dashboard (https://dydx-mev-comparison.streamlit.app/) where any user can upload a json file corresponding to the matches, and it automatically parses and shows in a table mode (where you can download a .csv file) the matches both by the BP and the expected validator matches, as well as order book discrepancy. 
