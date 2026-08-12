# Bitcoin Simulation Project --- BlockSim

This repository contains the modified version of the **BlockSim**
blockchain simulator used for the **CSE729 --- Blockchain and
Distributed Ledger** course project.

The project is based on the original BlockSim simulator developed by
**Maher Alharbi**. The original repository is available at:

https://github.com/maher243/BlockSim

The original simulator was used as the base implementation, and selected
source files were modified to complete the required experiments in this
project.

## Project Modifications

### 1. FIFO Transaction Ordering

A transaction-ordering toggle was added to support two modes:

-   **Fee-priority ordering** --- transactions are selected based on
    their fees, with higher-fee transactions given priority.
-   **FIFO ordering** --- pending transactions are selected according to
    their arrival order.

The selected ordering mode is also printed in the terminal during
execution.

### 2. Block Reward Halving

A simplified Bitcoin-style block reward halving mechanism was
implemented.

The reward is reduced by half after every configured number of blocks.
The halving interval can be changed through the simulation
configuration.

The project experiments use the following halving intervals:

-   20 blocks
-   40 blocks
-   60 blocks
-   80 blocks

## Experiments

The repository was used to perform the experiments required in the
CSE729 assignment:

-   **Task 1:** Effect of miner count on the percentage of mined blocks.
-   **Task 2:** Effect of block interval on stale rate.
-   **Task 3:** Comparison of FIFO and fee-priority transaction
    ordering.
-   **Task 4:** Effect of block reward halving on miner profit.

## Requirements

-   Python 3 or above
-   pandas
-   numpy
-   scikit-learn
-   XlsxWriter

Install the required packages using:

``` bash
pip install pandas numpy scikit-learn XlsxWriter
```

## Running the Simulator

The simulation parameters can be configured in `InputsConfig.py`.

For the Bitcoin model, configure:

``` python
model = 1
```

Then run:

``` bash
python Main.py
```

The simulator generates an Excel file containing the simulation results,
including blockchain information, mined blocks, stale blocks, and miner
rewards/profits.

## Repository Structure

Important files include:

-   `Main.py` --- starts the simulation.
-   `InputsConfig.py` --- simulation configuration and parameters.
-   `Transaction.py` --- transaction processing and ordering logic.
-   `Incentives.py` --- block reward and incentive mechanism.
-   `Statistics.py` --- generates simulation statistics and output
    files.
-   `Models/` --- blockchain model components.

## Attribution

This project is an academic modification of the original **BlockSim**
simulator.

**Original project:** Maher Alharbi, *BlockSim: An Extensible Simulation
Tool for Blockchain Systems*

**Original repository:** https://github.com/maher243/BlockSim

The BlockSim simulator and its original implementation are credited to
the original authors. The modifications in this repository were made
specifically for the CSE729 course project.

For more information about the original BlockSim simulator and its
research background:

https://www.frontiersin.org/articles/10.3389/fbloc.2020.00028/full

