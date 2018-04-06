# Technical Analysis Library in Python

You can use this library to add features to your finacial time series dataset.

### Volume

* Accumulation/Distribution Index (ADI)
* On-Balance Volume (OBV)
* On-Balance Volume mean (OBV mean)
* Chaikin Money Flow (CMF)
* Force Index (FI)
* Ease of Movement (EoM, EMV)
* Volume-price Trend (VPT)

### Volatility

* Average True Range (ATR)
* Bollinger Bands (BB)
* Keltner Channel (KC)
* Donchian Channel (DC)

### Trend

* Moving Average Convergence Divergence (MACD)
* Average Directional Movement Index (ADX)
* Vortex Indicator (VI)
* Trix (TRIX)
* Mass Index (MI)
* Commodity Channel Index (CCI)
* Detrended Price Oscillator (DPO)
* KST Oscillator (KST)
* Ichimoku Kinkō Hyō (Ichimoku)

### Momentum

* Money Flow Index (MFI)
* Relative Strength Index (RSI)

### Fundamental

* Daily Return (DR)
* Cumulative Return (CR)


# How to use

> virtualenv -p python3 virtualenvironment
> source virtualenvironment/bin/activate
> pip3 install ta

### Example adding all features

```python
import pandas as pd
from ta import *

# load datas
df = pd.read_csv('your-file.csv', sep=',')

# clean nan values
df = utils.dropna(df)

# add ta features
df = add_all_ta_features(df, "Open", "High", "Low", "Close", "Volume_BTC")

# fill nan values
df = df.fillna(method='backfill')
```


### Example adding one feature

```python
import pandas as pd
from ta.volume import *

# load datas
df = pd.read_csv('your-file.csv', sep=',')

# clean nan values
df = utils.dropna(df)

# add ta feature
df['cmf'] = chaikin_money_flow(df.High, df.Low, df.Close, df.Volume_BTC)

# fill nan values
df['cmf'] = df['cmf'].fillna(method='backfill')
```


If you don't know any feature you can visualize them in "visualize_features.ipynb".


# Deploy to developers

> pip3 install -r requirements.txt


# Based on:

* https://en.wikipedia.org/wiki/Technical_analysis
* https://github.com/FreddieWitherden/ta
* https://github.com/femtotrader/pandas_talib


# Credits:

Developed by Bukosabino at Lecrin Technologies - http://lecrintech.com

We are glad to receive any contribution, idea or feedback.
