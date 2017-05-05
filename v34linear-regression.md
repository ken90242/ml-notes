# Hypothesis

$$y\approx \sum_{i=0}^dw_ix_i$$

$$h(x) = w^Tx$$

# Error Measure

$$square\ error: err(\hat{y},y) = (\hat{y}-y)^2$$  $$x = y$$

### in-sample:$$$$

$$E_{in}(w) = \frac{1}{N}\sum^N_{n=1}(h(x_n)-y_n)^2$$

### out-sample:

$$E_{out}(w) = \varepsilon_{(x,y)\sim P}(w^Tx-y)^2$$



