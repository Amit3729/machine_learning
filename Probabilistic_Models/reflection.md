
Q. Answer in your own words: 'Give one concrete example from this
assignment where the fully Bayesian answer would have changed
a decision you might have made using only the MLE or a p-value.
Explain the mechanism — was it prior information, uncertainty
quantification, sequential updating, or the Bayesian-vs-frequentist
comparison?'


-> In Q2, when I computed the MLE for Group A_small (n=40), I got a single number — say 0.475 — and if I only had that, I probably would have told the VP "Month-to-month customers churn at 47.5%, we need to act now." A p-value against a null of 0.25 might have backed that up and made it look even more convincing.
But when I plotted the full Bayesian posterior, the 94% HDI was really wide — something like 0.30 to 0.63. That completely changed the picture. The posterior is not saying "reject or don't reject," it's saying "we genuinely don't know where the true rate is yet, it could be anywhere in this range." That's a very different message to give a VP who's about to approve a budget.
The mechanism here was two things working together — uncertainty quantification and prior information. The Beta(2,8) prior encodes the business belief that most segments churn below 30%. With only 40 observations the prior is contributing 10/(10+40) = 20% of the total weight, so it actively pulls the estimate down and forces the posterior to stay wider. The MLE just ignores all of that and gives you false confidence in a number from 40 data points.
What really drove this home for me was Q6. The sequential update showed exactly when P(θ > 0.25) crossed 90% — that's the point where I'd actually have enough evidence to act. The frequentist approach needed me to pre-specify the sample size before collecting any data. The Bayesian approach let me watch the evidence accumulate in real time and make the call when the data actually justified it. That's the part that felt most useful for a real business decision.