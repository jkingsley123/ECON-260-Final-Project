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

#### CONSTRAINED (SALARY CAP) PROBLEM WITH DIFFERENT TALENT LEVELS:

While the unconstrained and constrained models above are useful in theory, they do not reflect the reality of the professional soccer industry, in which teams consist of different types of players with different levels of talent. To address how the constrained model would change to align with this reality, I will examine the same question as before. However, rather than treating talent level as a single aggregate, I will consider it as two separate aggregates which represent the talent level of depth players as well as the talent level of star players.

New Variables:

$T_s = \text{aggregate talent from star players}$

$T_d = \text{aggregate talent from depth players}$

$p_s = \text{wage per unit of star talent}$

$p_d = \text{wage per unit of depth talent}$

$C = \text{salary cap}$ (same as previous problems)

$R(T_s, T_d) = R_s(T_s) + R_d(T_d) = \text{total revenue}$ (assumes diminishing marginal returns for each player type)

$\pi = R_s(T_s) + R_d(T_d) - p_s T_s - p_d T_d = \text{profit}$

New optimization problem, maximizing $\pi$ over $T_s, T_d$ under the salary cap:

$$\max_{T_s , T_d}\pi \quad \text{s.t.} \quad p_s T_s + p_d T_d \le C$$

Lagrangian:

$$\mathcal{L} = R_s(T_s) + R_d(T_d) - p_s T_s - p_d T_d + \lambda \big( C - p_s T_s - p_d T_d \big) \quad where \quad \lambda \ge 0$$ 

First-order conditions:

$$\frac{\partial \mathcal{L}}{\partial T_s} = R_s'(T_s) - p_s(1+\lambda) = 0\quad \Rightarrow \quad R_s'(T_s) = p_s(1+\lambda)$$

$$\frac{\partial \mathcal{L}}{\partial T_d} = R_d'(T_d) - p_d(1+\lambda) = 0\quad \Rightarrow \quad R_d'(T_d) = p_d(1+\lambda)$$

Divide each by it's wage:

$$\frac{R_s'(T_s)}{p_s} = \frac{R_d'(T_d)}{p_d} = 1 + \lambda$$

The heterogenous-talent constrained model above extends the baseline salary cap framework by showing that a cap affects not only how much talent a professional soccer club acquires, but also how it allocates spending across different types of players. When the salary cap is non-binding, the club behaves as in the original unconstrained case: it invests in each type of talent until the marginal revenue generated by that talent equals its respective wage rate, leading to independent optimal choices for star and depth players. In this scenario, the salary cap has no real economic effect and does not distort roster composition. However, when the salary cap is binding, as is the case here, the club can no longer choose each talent type independently. Rather, it must allocate its limited payroll so that the marginal revenue generated per dollar spent is equalized across star and depth players. Even though the marginal revenue of additional star or depth talent may still exceed its wage, the cap forces the club to stop investing and reallocate spending toward the talent mix that maximizes returns under the constraint. As a result, salary caps do not simply reduce overall roster quality; they actively reshape roster composition by limiting the concentration of high-return talent, particularly star players who generate large marginal revenue but are costly. Economically, this implies that salary caps compress not only talent across clubs but also the distribution of talent within teams, disproportionately constraining high-revenue clubs while pushing all clubs towards more similar roster structures. This model therefore highlights a deeper trade-off faced by leagues: salary caps promote competitive balance not only by reducing spending disparities, but also by restricting clubs' ability to specialize in high-impact talent, potentially reducing aggregate league revenue and on-field quality.

#### CRITICAL DISCUSSION & CONCLUSION:

While my models provide a clean and intuitive framework for analyzing how salary caps shape a professional soccer club's roster decisions, their simplicity still introduces important limitations. The extension to heterogenous talent improves on the baseline constraint model by distinguishing between star and depth players and showing how a binding salary cap affects not only total spending, but also the composition of the roster. However, even this richer framework remains highly simplified and stylized. Player types are treated as homogenous within categories, wages are fixed and exogenous, and the model abstracts from key institutional features of professional soccer such as transfer fees, contract lengths, and bonuses. Revenue is also modeled as a deterministic and separable function of talent, ignoring uncertainty as well as external factors such as injuries, broadcasting deals, and international competition. As a result, the models likely overstate how smoothly clubs can reallocate spending under a salary cap and understate both the strategic and dynamic complexities of real roster management.

Despite these limitations, there are several ways to extend my findings beyond the largely theoretical results presented above. One natural extension would be to compare how different types of caps - soft caps, luxury taxes, or minimum salary floors, for example - affect talent distribution across clubs, competitive balance, and long-run league outcomes. There's also potential to apply the models to real data; estimating a revenue-talent function with real team performance metrics, player valuation databases, and wage bill data could allow for empirical tests of how closely actual clubs behave relative to the models' predictions. The theoretical framework could also be easily adapted to other professional sports leagues like the NFL or NBA to study cross-sport differences in spending power and competitive parity. Finally, the model could serve as a foundation for policy analysis; leagues could use my previous suggestions to compose a richer version of this model and evaluate how tightening or relaxing salary caps would affect competitiveness, financial stability, or player mobility, making the project relevant for both academic and practical decision-making contexts.

#### AI CITATION:

Throughout this project, I used ChatGPT to clarify the logic of solving constrained optimization problems and to assist with debugging issues in the code I used for making my equations and importing graphs. 
