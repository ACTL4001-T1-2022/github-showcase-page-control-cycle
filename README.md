# SOA Case Study 2022: Rarita Football League

### Team Control Cycle
Sumeet Singh, James Li, Asel Lewliyadde, Ngoc Phuong Dung Vo, Kawitsara Boonvisud


## Project Outline
> This repository showcases our attempt at the [SOA Student Case Study 2022](https://www.soa.org/research/opportunities/2022-student-research-case-study-challenge).  

We were proposed with buiding a competitive soccer team to build a long-term brand for Rarita's football program that will propel economic growth and prosperity in Rarita. We employed methods such as gradient boosting machines and linear regression to provide rationale to our team selection. With our proposed squad, we then proposed an implementation plan with the assumptions that our team selection will lead to a competitive result in the FSA league, and an economic analysis was then conducted that studied the impacts of the year cashflows of this team to Rarita's GDP, GNI and other relevant measures. Additionally, preventative measures such as building out a larger squad, diversifying assets and purchasing indemnity insurance are part of the mitigating measures made to de-risk the potential scenarios associated with constructing an elite football team. 

## Team Selection
Our initial 11 player squad consisted of the following players:
|Position|Player|Initial Salary|
|:---|:---|:---|
|FW|X. Petersen|5,120,000|
|FW|N.Yamashita|8,270,000|
|FW|D. Bengtsson|8,190,000|
|MF|O.Wanjala|1,750,000|
|MF|X. Leroy|5,630,000|
|MF|F. Chin|1,340,000|
|DF|B. Ayuba|21,950,000|
|DF|T. Okoro|730,000|
|DF|Q. Sano|7,200,000|
|DF|Q.bin Ismail|920,000|
|GK|F. Akuma|15,461,250|

To formalise our procedure for team selection we produced player ratings to provide a clear numeric comparison between the numerous players that could be chosen by aggregating weighted key performance indicators. A generalised boosting algorithm was trained to determine the player statistics that are key in predicting the success of the team they belong to through the variable importance. The variable importance  acted as a proxy to then determine the weights to apply to key player performance indicators to then be aggregated into the overall rating. The plot below shows the relative influence as determined by the boosting algorithm and was used to assign weights to the individual key player indicators to provide an aggregate rating. This process was repeated for all the 4 positions.

![Figure 1](Shooting%20Rel%20Influence.png)

## Implementation Plan

We projected the revenues and expenses from having a national football team for the next 10 years. Revenues and expenses were each categorised into 3 main groups, including matchday, broadcast and commercial for the former, players' salaries, other staff's salaries and other expenses for the later. In the first 5 years, revenues were expected to increase with inflation and have no significant changes, except for commercial revenue with 6% increase in the first year due to new contracts and sponsorship signed. In contrast, apart from increasing with inflation, expenses were forecasted to rise at a significant rate for the first few years, due to staffs' salaries of a new established team and a large amount of investment required for marketing campaign, social media promoting, facility management and the various training personnel. 
After year 5, when the team was forecasted to rank within top 10 of the FSA league, revenues and expenses were expected to have significant impacts. Revenues were expected to boost, as there were more recognitions, reputation and sponsorships. All staff's salaries would increase, so as the cost of advertising and marketing, resulting in a rise in expenses. Up until before the national team win FSA championship, there would be small increases in both revenues and expenses to sustain top 10 ranking. 
The national team was expected to win in the end of year 9. As a result, in year 10, there would be big impacts on both revenues and expenses. 

![Figure 2](Proposed%20Expenses.png)
![Figure 3](Proposed%20Revenues.png)

## Economic Impact
The increased investment from the team, paying salaries to players, other personnel and facilities, lead to high private consumption. The team will regularly invest a substantial proportion of its cash in risk free assets with varying maturities to grow its funds. These contribute to higher gross private investment, leading to a higher GDP per capita. In the first year, the injection of a considerable sum of cash into the team would also significantly boost the GDP. The following table describes the relative increase in the GDP that is expected compared to the forecasted GDP. Growth in the expected GDP is around 0.3% per year which has been calculated using conservative assumptions but will contribute to slow prosperous development of the economy. Rarita???s better players were loaned for 10% over their salary, assuming that their salary would only increase by inflation each year, however, larger jumps in salary are expected when assuming that Rarita will be successful this would contribute to increases to the forecasted GNI. 

|Year|Expected Increase in GDP per Capita|Expected Increase in GNI per Capita|
|:---|:---|:---|
|2022|84.26|84.26|
|2023|40.97|40.97|
|2024|60.90|63.06|
|2025|39.74|41.92|
|2026|40.05|42.25|
|2027|41.13|43.34|
|2028|40.83|43.04|
|2029|38.96|41.19|
|2030|40.83|43.05|
|2031|45.36|47.58|

## Risk Consideration

As part of our risk considerations, we aimed at creating a safe sporting environment for our players whilst managing the various liability and investment risks that could potentially occur. We broke this down into 4 main areas; health, reputational, operational and investment risk. The health risk was quite easy to identify and mainly concerns the fitness and ongoing health status of our players. We added extra players into the squad in case any sickness or injuries affect our starting 11. As part of our operational risks, we want to ensure that our projected revenues are not too volatile and that it can sustain our costs. We aim to allocate into stable revenue streams such as extending broadcasting contracts. Moreover, we can mitigate investment risks by diversifying our investments into both short term assets and long term bonds.

## Assumptions
- Each FSA season will be played out over the course of one calendar year. We have assumed that at the end of the 5th year our selected team will be placed inside the top 10, and finally in the 9th year of play we will win the FSA championship. These assumptions are reflected in the changes to revenues and expense items mentioned in the implementation plan. 
- All revenues and expense documented (including player salaries) are all payable at the end of each year.
- Interest rates and inflation rates used throughout the analysis were assumed to follow exponential smoothing time series estimates.
- For per capita estimates, we projected Rarita???s population using linear regression. 


## Data Limitations
- When using our boosting modelling method, we had to omit several variables that contained a large amount (often >50%) of spurious negative values: for example, negative attempts, goals and shots, as these do not make sense.
- To avoid NA player ratings, we imputed the missing data using predictive mean matching. For our boosting model however, players with any missing values were removed as they only made up a small percentage of the available dataset, to keep our rating model as accurate as possible.
- Player salaries were missing for some players that we had chosen and therefore we imputed the salary with the average of those players (up to 10) with the same or similar rating. 
- The analysis of player ratings was conducted using the top 3 teams of the 2021 league results as the data had a more representative sample size for the key player metrics the model was to consider.


## References
Kalen, A., Ezequiel, R., Sal de Rellan-Guerra, A., & Lago-Penas, C. (2019). Are Soccer Players Older Now Than Before? Aging Trends and Market Value in the Last Three Decades of the UEFA Champions League. Performance Analysis in Sport. 

J. Almulla and T. Alam, "Machine Learning Models Reveal Key Performance Metrics of Football Players to Win Matches in Qatar Stars League," in???IEEE Access, vol. 8, pp. 213695-213705, 2020, doi: 10.1109/ACCESS.2020.3038601. 

Cortez, A.; Trigo, A.; Loureiro, N. Football Match Line-Up Prediction Based on Physiological Variables: A Machine Learning Approach. Computers 2022, 11, 40. https://doi.org/10.3390/ computers11030040 

Ajadi, T., Ambler, T., Udwadia, Z. and Wood, C., 2020.???Annual Review of Football Finance 2020. [online] www2.deloitte.com. Available at: <https://www2.deloitte.com/content/dam/Deloitte/uk/Documents/sports-business-group/deloitte-uk-annual-review-of-football-finance-2020.pdf> [Accessed 20 March 2022]. 



