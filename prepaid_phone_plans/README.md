# Prepaid Phone Plans (focus on statistical analysis)

:point_right: View the **notebook**[here]()

## In this folder

| File name | Description |
| --- | --- |
|*megaline_calls.csv* | Data on user phone calls |
|*megaline_internet.csv* |Data on user internet use |
|*megaline_messages.csv*| Data on user messaging|
|*megaline_plans.csv*| Data on phone plans|
|*megaline_users.csv*| Data on users |
|*prepaid_phone_plans_analyis.ipynb* | Comparison of two prepaid phone plans |


## Project Description

### Objective
Telecom operator, Megaline, offers its clients two prepaid plans, Surf and Ultimate. The commercial department wants to know which of the plans brings in more revenue in order to adjust the advertising budget.
The following is a preliminary analysis of the plans based on a relatively small client selection: 500 clients. The analysis covers who the clients are, where they're from, which plan they use, and the number of calls they made and text messages they sent in 2018. 

<u>Description of the plans</u>
Note: Megaline rounds seconds up to minutes, and megabytes to gigabytes. For calls, each individual call is rounded up: even if the call lasted just one second, it will be counted as one minute. For web traffic, individual web sessions are not rounded up. Instead, the total for the month is rounded up. If someone uses 1025 megabytes this month, they will be charged for 2 gigabytes.

### Data 
1. **Surf**
Monthly charge: $20
500 monthly minutes, 50 texts, and 15 GB of data
After exceeding the package limits:
1 minute: 3 cents
1 text message: 3 cents
1 GB of data: $10

2. **Ultimate**
Monthly charge: $70
3000 monthly minutes, 1000 text messages, and 30 GB of data
After exceeding the package limits:
1 minute: 1 cent
1 text message: 1 cent
1 GB of data: $7

1. The users table (data on users):
- `user_id` — unique user identifier
- `first_name` — user's name
- `last_name` — user's last name
- `age` — user's age (years)
- `reg_date` — subscription date (dd, mm, yy)
- `churn_date` — the date the user stopped using the service (if the value is missing, the calling plan was being used when this database was extracted)
- `city` — user's city of residence
- `plan` — calling plan name

2. The calls table (data on calls):
- `id` — unique call identifier
- `call_date` — call date
- `duration` — call duration (in minutes)
- `user_id` — the identifier of the user making the call

3. The messages table (data on texts):
- `id` — unique text message identifier
- `message_date` — text message date
- `user_id` — the identifier of the user sending the text

4. The internet table (data on web sessions):
- `id` — unique session identifier
- `mb_used` — the volume of data spent during the session (in megabytes)
- `session_date` — web session date
- `user_id` — user identifier

5.The plans table (data on the plans):
- `plan_name` — calling plan name
- `usd_monthly_fee` — monthly charge in US dollars
- `minutes_included` — monthly minute allowance
- `messages_included` — monthly text allowance
- `mb_per_month_included` — data volume allowance (in megabytes)
- `usd_per_minute` — price per minute after exceeding the package limits (e.g., if the package includes 100 minutes, the 101st minute will be charged)
- `usd_per_message` — price per text after exceeding the package limits
- `usd_per_gb` — price per extra gigabyte of data after exceeding the package limits (1 GB = 1024 megabytes)

### Libraries to run the notebook locally
<b> *Python version 3.8.8* </b>
|Library| Version|
| --- | --- |
|pandas|1.3.1|
|numpy|1.19.2|
|seaborn| 0.11.2|
|matplotlib| 3.3.2 |
|scipy|1.5.2|
|math|3.8.5|

##Conclusion
1. Popularity:
- 68% of customers prefer the Surf plan to the Ultimate plan.

2. Exceeding free limits:
- More than 1/2 of the bills for the surf plan exceed the base fee, accounting for nearly a quarter of the users of this plan.
- In fact, nearly 1/2 of surf users even exceeded the ultimate base fee at least once accounting for 1/4 of all surf bills.
- On the other hand, few users of the ultimate plan are going over their base fees each month.
- Overal annual revenue in 2018 was 45% higher from the surf plan. However, revenue per user was 16% higher for the ultimate plan.

3. The difference in revenue is statistically significant:
- More users are on the surf plan which is what accounts for the higher revenue, but the ultimate plan generates more revenue.
- Possibly pointing out to the surf users who have gone over their limit once, immediately following that event, that they may benefit from the ultimate plan, could encourage them to switch to the plan that is more profitable for the company.
- User activity was only mildly guided by their plan. Median and means for the Ultimate plan were only slightly higher than for the Surf plan for call duration and mb used; for messages the differences between the 2 plans was slightly more significant.

4. The difference between the average revenue from users in NY-NJ area vs. other regions is not statistically significant.
