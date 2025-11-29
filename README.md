# Jack Kingsley - ECON 260 Final Project

#### QUESTION:

How does a salary cap affect a professional soccer club's optimal roster investment and profit?

#### VARIABLES:

Before setting up a model that can accurately represent a professional soccer club's roster investment choices and profit under a salary cap, I must first define several variables relating to the types of players the club signs (talent level), the wages these players earn, the salary cap in place, the revenue function, and the profit formula:

$T = \text{aggregate talent level of players}$

$R(T) = \text{revenue function}$

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

#### UNCONSTRAINED PROBLEM:

The professional soccer club's uncontrained optimization problem is:

$$\max_T \ \pi(T) = R(T) - pT$$

The first-order condition is:

$$R'(T) = p$$

Because we assumed that $R''(T) < 0$ (diminishing marginal returns), this solution is a maximum.


If $R'(0) \le p$, the solution is a corner and the club chooses:

$$T^* = 0$$

In the unconstrained model above, the professional soccer club invests in talent until the marginal revenue product of talent equals its marginal cost, $R'(T^*) = p$, meaning the final unit of talent adds exactly as much revenue as its costs. Because revenue demonstrates diminishing marginal returns, early units of talent such as star signings generate disproportionately large benefits, while additional "depth" players contribute less. This also implies that if $R'(0) < p$, the club optimally hires no talent, reflecting why low-revenue clubs often underinvest in player recruitment or fail to compete with other clubs. Most importantly, this unconstrained model shows that without a salary cap, nothing limits richer clubs (e.g. Manchester City, PSG in real life) from accumulating far more talent than others, creating competitive imbalance and motivating league interventions such as caps or revenue sharing.

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

$$T = \frac{C}{p}$$
