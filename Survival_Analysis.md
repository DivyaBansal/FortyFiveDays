- Censoring:
	Some events are inconclusive/uncertain in determining the predictor, as their inputs dropout i.e. not recorded after a certain time. These points can be dropped out all together or their information can still be leveraged for determining survival until the time they are present. These are called censored data points.

- Survival time represents the time at which the event of interest occurs (such as death)

- `True censoring time:` C

- `True survival time:` T

- `Y = min(T,C)`

- Independent censoring vs dependent censoring: we need to take into account if the censoring is random or dependent on individual characteristics like males are more likely to dropout than females.

- Survival function:
	Probability that an instance can survive for longer than a certain time *t*
	$$S(t) = Pr(T>=t)$$

- Cumulative Density function:
	Probability that the event of interest occurs earlier than *t*
	$$ F(t) = 1 - S(t)$$

- Death Density function:
	$$f(t) = \frac{dF(t)}{dt} = -\frac{dS(t)}{dt} $$

- Hazard function:
	probability the event of interest occurs in the next instant, given survival to time t
	$$h(t) = \frac{f(t)}{S(t)} = - \frac{d[lnS(t)]}{dt}$$

- Cumulative hazard function:
	$$ H(t) =\int_0^t h(u) \,du $$
	 $$ Survival function,\: S(t) = exp(-H(t))$$

- Special Evaluation Metrics:
	- Concordance index (C-Index):
		Rank order statistic for predictions against true outcomes and is defined as the ratio of the concordant pairs to the total comparable pairs.
	 
	 Given comparable instance pair (*i*, *j*) and t<sub>i</sub> and t<sub>j</sub> are the actual observed times and S(t<sub>i</sub>) and S(t<sub>j</sub>) are the predicted survival times,
	 The pair (*i*, *j*) **is concordant** if t<sub>i</sub> > t<sub>j</sub> and S(t<sub>i</sub>) > S(t<sub>j</sub>)
	 The pair (*i*, *j*) **is discordant** if t<sub>i</sub> > t<sub>j</sub> and S(t<sub>i</sub>) < S(t<sub>j</sub>)
	 
	 So, if your predicted event ordering is exactly equal to the actual event ordering, the concordance index would be 1.	
	
	- Brier score
	- Mean absolute error