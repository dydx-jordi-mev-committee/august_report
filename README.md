This is a simple repository containing two folders:

- Liquidation blocks
- Non liquidation blocks

Inside each folder, we've uploaded a set of JSON files corresponding to the logs by the MEV Committee node, where we see the block proposer matches and the ones expected by our validator, as well as the liquidations and block prices for each asset.

Additionally, we share a few queries used for querying Numia data useful for each analysis. On top of that, the committee has also created the following simple streamlit dashboard (https://dydx-mev-comparison.streamlit.app/) where any user can upload a json file corresponding to the matches, and it automatically parses and shows in a table mode (where you can download a .csv file) the matches both by the BP and the expected validator matches, as well as order book discrepancy. 

In order to replicate the initial steps we do when analyzing a block with high discrepancy, this would be the procedure:

- Once we have a block with high order book discrepancy, we pull the logs from our node.
- With those logs, using the streamlit app, we can see the traders and their matches, price and volume.
- We take query_1.sql, and look for our block number, execute it using numia. This way, we obtain the maker and taker trade_id.
- With the different traders and trade IDs, we look at query_2.sql which queries the mempool via Numia and we filter by the specific trade_ids, trader, and market. We can then see the arrival time at the mempool according to Numia.
- Taking all the previous information, we dig deeper or stay at a surface level trying to understand why the matches took place the way they occured.


