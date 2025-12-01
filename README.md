# Jack Kingsley - ECON 260 Final Project

#### INTRODUCTION: 

As a lifelong fan of professional soccer, I've always thought it was very interesting to hear about how many European powerhouses - such as Chelsea, PSG, Barcelona, and Manchester City - could be so dominant on the field while simultaneously being involved in business scandals off of it. While these clubs have primarily been accused of breaching Financial Fair Play regulations through violations such as failure to disclose accurate financial statements or approach break-even spending, they have consistently adhered to the salary cap regulations within their respective leagues; these caps have seen such clubs face dilemmas of selling or terminating the contracts of certain players who make significant wages. In this project, I will examine how salary caps affect a professional soccer club's optimal roster investment and profit through a step-by-step procedure. First, I will define relevant variables and list important assumptions that relate to these variables. Next, I will create an unconstrained optimization model and walk through the solution to discuss how a club's roster investment and revenue are affected when there's no salary cap in place. Afterwards, I will create a constrained optimization model and walk through the solution to show how a salary cap affects a club's roster investment and revenue. Lastly, I will critically discuss the limitations of my project's models and conclude with possible extensions of my findings.

#### QUESTION:

How does a salary cap affect a professional soccer club's optimal roster investment and profit?

#### VARIABLES:

Before setting up a model that can accurately represent a professional soccer club's roster investment choices and profit under a salary cap, I must first define several variables relating to the types of players the club signs (talent level), the wages these players earn, the salary cap in place, the revenue function, and the profit formula:

$T = \text{aggregate talent level of players}$

$R(T) = \text{revenue function}$

$MR(T) = \text{marginal revenue function}$

$p = \text{players' wage}$

$C = \text{salary cap}$

$\pi(T) = R(T) - pT, \quad \text{s.t. } pT \le C$

#### ASSUMPTIONS:

This model simplifies various realities of the professional soccer industry in order to make the equations below as clear as possible:

Assumption #1: A single representative club's objective is to maximize short-run profit under the salary cap constraint (i.e. the salary cap constrains the club's payroll only during the current season)

Assumption #2: $T \ge 0$ (i.e. aggregate talent/quality within a roster cannot be negative in reality)

Assumption #3: $p > 0$, so $\text{total wage} = pT$ (as implied by the salary cap, $pT \le C$)

Assumption #4: Match-related revenue is an increasing, concave function of talent: $R = R(T)$

Assumption #5: $R'(T) > 0$ and $R''(T) < 0$ (i.e. diminishing marginal returns of extra talent)

Assumption #6: Non-wage costs are ignored

Assumption #7: players' wage rate is held constant

#### UNCONSTRAINED PROBLEM:

The professional soccer club's uncontrained optimization problem is:

$$\max_T \ \pi(T) = R(T) - pT$$

The first-order condition is:

$$\frac{\partial \pi}{\partial T} = R'(T) - p$$

$$R'(T) - p = 0$$

$$R'(T) = p$$

Because we assume $R''(T) < 0$ (diminishing marginal returns), this solution corresponds to a maximum.

Corner Solution:

If $R'(0) \le p$, the marginal revenue from the first unit of talent isn't enough to cover its cost, so the optimal choice is:

$$T^* = 0$$

On the other hand, if the marginal revenue from the first unit of talent is enough to cover its cost, then the club's optimal choice is to invest in the exact level of talent that produces $MR(T) = p$. In the graph below, for example, the club's optimal choice is $T^* = 6.75$, as that is the point on the graph where marginal revenue and players' wage intersect.

![image alt](https://github.com/jkingsley123/ECON-260-Final-Project/blob/99760db0febe9bed7e96ee1d494e0cb4997651b2/Optimal%20Talent%20Decision.png)

In the unconstrained model above, the professional soccer club invests in talent until the marginal revenue product of talent equals its marginal cost, $R'(T^*) = p$, meaning the final unit of talent adds exactly as much revenue as its costs. Because revenue demonstrates diminishing marginal returns, early units of talent such as star signings generate disproportionately large benefits, while additional "depth" players contribute less. This also implies that if $R'(0) \le p$, the club optimally hires no talent, reflecting why low-revenue clubs often underinvest in player recruitment or fail to compete with other clubs. Most importantly, this unconstrained model shows that without a salary cap, nothing limits richer clubs from accumulating far more talent than others, creating competitive imbalance and motivating league interventions such as caps or revenue sharing.

#### CONSTRAINED (SALARY CAP) PROBLEM:

With a salary cap now in place, the professional soccer club now solves the optimization problem:

$$\max_T \ \pi(T) = R(T) - pT \quad \text{s.t.} \quad pT \le C$$

The corresponding Lagrangian is:

$$\mathcal{L} = R(T) - pT + \lambda (C - pT)$$

The first-order condition simplifies to:

$$\frac{\partial T}{\partial L} = R'(T) - p - \lambda p = 0$$

$$R'(T) = p(1+\lambda)$$

If the salary cap is non-binding, then $C - pT > 0$, so the FOC is:

$$R'(T) = p$$

If the salary cap is binding, then $C - pT = 0$, meaning:

$$T^* = \frac{C}{p}$$

The constrained model above shows that a salary cap fundamentally changes how a professional soccer club allocates talent compared to the previous unconstrained case. When the salary cap is non-binding, the club behaves exactly as before: it invests in talent until the marginal revenue generated by the last unit of talent equals the players' wage rate. In this scenario, the salary cap has no real economic effect; it simply sits above the club's preferred spending level. However, when the salary cap is binding, the club cannot reach the point where $R'(T) = p$; instead, it's forced to stop increasing talent at $T = \frac{C}{p}$, even though the marginal revenue of talent is still greater than its cost. This means that the club is operating inside its profit frontier; it would want to recruit more talent, and doing so would raise profit, but the cap prevents it. As a result, the salary cap compresses roster quality across the league by cutting off investment precisely where returns are highest, disproportionately limiting clubs that would otherwise spend more on talent. Economically, this illustrates narrowing the gap between high-revenue and low-revenue teams. The model therefore highlights the trade-off leagues face: improved parity comes at the cost of reducing the potential revenue and on-field quality that top-spending clubs could otherwise achieve without a salary cap in place.

#### CRITICAL DISCUSSION & CONCLUSION:

While my models provide a clean and intuitive way to analyze how salary caps shape a professional soccer club's optimal roster investment, their simplicity also introduces important limitations. Treating talent as a single aggregate variable overlooks the multidimensional nature of real rosters, where star players, depth or rotational players, and youth prospects contribute differently to their club's revenue and success, both on and off the field. The models also assume a constant wage rate and ignore critical factors that affect a club's spending decisions in practice, including transfer fees, amortization, performance-based bonuses, and non-wage operating costs. Additionally, revenue is modeled as a deterministic, concave function of talent, even though real clubs' revenues are uncertain and influenced by many other external factors (e.g. broadcast deals, injuries that impact on-field performance, fan engagement, and international competition). These simplifications mean that the results likely overstate how smoothly clubs adjust to a salary cap and understate the strategic complexity of real roster decisions. To address these limitations, future models could incorporate heterogenous player quality and wages, stochastic revenue, multi-season planning, and the inclusion of additional financial constraints such as transfer budgets or Financial Fair Play rules.

Despite these limitations, there are several ways to extend my findings beyond the largely theoretical results presented above. One natural extension would be to compare how different types of caps - soft caps, luxury taxes, or minimum salary floors, for example - affect talent distribution across clubs, competitive balance, and long-run league outcomes. There's also potential to apply the models to real data; estimating a revenue-talent function with real team performance metrics, player valuation databases, and wage bill data could allow for empirical tests of how closely actual clubs behave relative to the models' predictions. The theoretical framework could also be easily adapted to other professional sports leagues like the NFL or NBA to study cross-sport differences in spending power and competitive parity. Finally, the model could serve as a foundation for policy analysis; leagues could use my previous suggestions to compose a richer version of this model and evaluate how tightening or relaxing salary caps would affect competitiveness, financial stability, or player mobility, making the project relevant for both academic and practical decision-making contexts.

#### AI CITATION:

Throughout this project, I used ChatGPT to clarify the logic of solving constrained optimization problems and to assist with debugging issues in the code I used for making my equations and importing graphs. 
