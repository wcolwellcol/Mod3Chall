# Mod3Chall
Repo for Week 3 Challenge of Fintech Course in which I attempt to identify arbitrage opportunities over a months long span in 2018. This is retroactive calculation and not actionable insight, but is still interesting to look at.

---
## Technologies
This code was written using Python 3.7.13. I found it very helpful to work in jupyter notebooks as it is nearly a necessity to be able to run segmented parts of the code. However, one could accomplish this goal using other technologies or choose to not even do so whatsoever.

My OS is Ventura 13.2.1 though it should be fine on most others. Note that the CLI in any screenshots may look different on different OSs.
I used conda to manage all of my packages.
Packages used:

csv 1.0

---
## Installation
The user should not have to install any packages, but if one somehow finds that they do I would recommend using` pip install`
For example,
`pip install <package name>`

If you are unsure of what python version (if any) you have, here is a handy link to troubleshoot those issues. 
[Installing python](https://realpython.com/installing-python/)



---
### Usage
The goal of this project is to identify historical arbitrage opportunities for bitcoin. We compare the price history for bitcoin from two exchanges and identify areas in which profitable arbitrage exists. 

Code can be found in the following notebook [crypto_arbitrage.ipynb](https://github.com/wcolwellcol/Mod3Chall/blob/main/crypto_arbitrage.ipynb).

Data for this project is sourced from two csvs: [bitstamp.csv](https://github.com/wcolwellcol/Mod3Chall/blob/main/Resources/bitstamp.csv) and [coinbase.csv](https://github.com/wcolwellcol/Mod3Chall/blob/main/Resources/coinbase.csv).

In general, the code can be split into 3 different categories: data collection, data preparation, and data analysis.

Data collection is simply reading in the two above referenced csvs.
`bitstamp = pd.read_csv(Path('Resources/bitstamp.csv'), index_col='Timestamp', parse_dates = True, infer_datetime_format = True)`

Note the use of the parameters which enable us to use datetime objects as the index of the dataframe. This will be super helpful later on during analysis.

Data preparation is simply handling null values and examining duplicates. In this instance, I chose to drop NaNs as there are so many values in the dataframe it should interfere with any descriptive statistic calculation. Also, the other standard way of handling the NaN values (using the mean) would interfere with arbitrage calculation as it would artificially create significant spreads. As for duplicates, for which there were many, it does not make sense to drop them as it is entirely feasible that stocks are returning to the same prices over spans of time.


## Contributors

This code was written by me, but the framework was provided by the Columbia Fintech Bootcamp

## License

MIT License

Copyright (c) [2023] [willcolwell]

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.