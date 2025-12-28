# Stock-price-prediction
**Author:** Rizan Atlanta (Fariha Hossain Rizan).<br/>
**Project type:** Data science / Machine Learning.<br/>
**Status:** Completed.

## Abstract
This project investigates short-term stock price forecasting through a comparative evaluation of baseline heuristics and deep learning–based time-series models. Rather than aiming for unrealistic predictive accuracy, the study emphasizes methodological rigor, transparent benchmarking, and critical interpretation of results in a highly stochastic financial domain.

## Research Motivation

Financial markets exhibit:

- non-stationarity

- structural breaks

- high noise-to-signal ratios

These properties make stock price prediction a theoretically and empirically challenging problem. The motivation of this project is to examine whether increased model complexity—specifically recurrent neural networks—offers measurable and justifiable performance gains over simple statistical baselines under realistic constraints.

## Dataset
dataset : yfinance (AAPL)
The dataset consists of historical daily stock prices, including:
- Open
- High
- Low
- Close
- Volume
All experiments strictly adhere to temporal causality, ensuring that no future information is used during training or evaluation.

## Methodology
Data Preprocessing

To maintain experimental validity, the following steps were applied:

1. *Chronological train–test split*<br/>
Preserves real-world forecasting conditions and prevents data leakage.

2. *Missing value handling*<br/>
Forward-filling applied to retain temporal continuity.

3. *Normalization*<br/>
Min–Max scaling applied to improve numerical stability during training.

4. *Sequence construction*<br/>
A sliding-window approach was used to convert raw time-series data into fixed-length input sequences for supervised learning.

## Model evaluated 

**Long Short-Term Memory (LSTM)**

An LSTM network was trained to model temporal dependencies and non-linear patterns within the data.

- Key characteristics:

- Sequential input representation.

- Gated memory mechanism.

- Regression output for continuous price prediction.

LSTMs are well-suited for time-series modeling due to their ability to retain long-range contextual information.

**Naive Baseline**

A naive forecasting strategy was implemented where the next time step is predicted using recent historical values.

Purpose:

- Establish a minimum performance threshold.

- Prevent overestimation of deep learning effectiveness.

Baseline models serve as a critical reference point in time-series research.

## Evaluation Strategy

Model performance was assessed using:

Model performance was evaluated using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

MAE provides an interpretable measure of average prediction error, while RMSE penalizes larger deviations more heavily, making it sensitive to periods of high volatility. Using both metrics allows for a more balanced assessment of forecasting performance.

## Model comparison

| Model                | MAE  | RMSE |
| ---------------------|------|------|
| Naive Baseline Model | 2.73 | 4.09 |
| LSTM                 | 5.57 | 7.72 |

Interestingly, the naive baseline outperformed the LSTM model across both MAE and RMSE metrics. This result highlights the inherent difficulty of short-term financial forecasting and aligns with existing literature suggesting that simple heuristics often remain competitive in low signal-to-noise environments. The findings emphasize the importance of baseline benchmarking and caution against assuming that increased model complexity necessarily leads to improved predictive performance.


## Analysis

The naive baseline outperformed the LSTM model across both evaluation metrics. The baseline achieved a MAE of 2.73 and RMSE of 4.09, compared to the LSTM’s MAE of 5.57 and RMSE of 7.72. This indicates that simple historical heuristics provided more reliable short-term predictions than the deep learning model.

The results suggest limited exploitable temporal structure in the dataset and highlight the risk of overfitting when applying complex models to noisy financial time-series. The consistency of this performance gap across both MAE and RMSE reinforces the importance of baseline benchmarking and cautions against assuming that increased model complexity guarantees improved predictive performance.


## Unexpected Observation
One unexpected observation during experimentation was that the LSTM model consistently underperformed the naive baseline. This prompted further inspection of overfitting behavior and reinforced the understanding that financial time-series often lack stable, exploitable patterns at short horizons

## References

- Hochreiter, S., & Schmidhuber, J. (1997). Long Short-Term Memory. Neural Computation.

- Tsay, R. S. (2010). Analysis of Financial Time Series.

- Brownlee, J. (2018). Deep Learning for Time Series Forecasting.


## DEMO screenshots
- Data Overview:<br/>
  https://drive.google.com/file/d/1HGk206PjGsOpJ3vot1ZWZyXBR8cTLaya/view?usp=sharing
- LSTM model summary:<br/>
  https://drive.google.com/file/d/12c2AWEj-sER3mw519xBTGHUBRchbb0JJ/view?usp=sharing
- Graphical show by LSTM of actual and predicted stock price:<br/> https://drive.google.com/file/d/1SrqCQp_bMYDPhlT11lJqbIRcpYdiVA7A/view?usp=sharing
- Graphical show of actual and predicted stock price by the comparison of LSTM model and Naives Baseline Model:<br/>
  https://drive.google.com/file/d/1BnCJ-jdeaaVkJ5yF4LPxC-cwdkhbwfEn/view?usp=sharing
- Model comparison table:<br/>
  https://drive.google.com/file/d/16ihAssmsupKmo8Xuyv7ZjNJG-feB3Yj0/view?usp=sharing

## Conclusion
This study demonstrates a disciplined, research-oriented approach to time-series forecasting by grounding deep learning experimentation in baseline comparison and critical analysis. The findings emphasize that in financial domains, model evaluation and interpretability are as important as raw performance.

This project is solely made for personal data science exploration and growth.

