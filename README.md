# Call-Centre-Trends-Analysis-with-Power-BI
Visualizing customer and agent behavior.

**Background**

The aim of this exercise is to look into transparency and insight into the data at the Call Centre. For example: total number of calls answered and abandoned, speed of answer, length of calls, overall customer satisfaction and any other relevant observations. I need to create a great visualization in Power BI that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset, which will later be used by management for decision making.

**Possible KPIs include (to get you started, but not limited to):**

- Overall customer satisfaction
- Overall calls answered/abandoned
- Calls by time
- Average speed of answer
- Agent’s performance quadrant -> average handle time (talk duration) vs calls answered

**Data Source**

This data was provided by PwC Switzerland as part of the project task, as a virtual intern through Forage.

**Exploratory data analysis (EDA)**

I had to export data in Power BI desktop and in transformation phase, I had a glance of it. The data consists of 10 columns and 500 rows. The columns are Call Id, Agent, Date, Time, Topic, Calls Answered, Resolved Calls, Speed of answer in seconds, Average Call Duration and Satisfaction Rating.

The data given comprises of seven days of the week, Monday to Friday for first three months of the year 2021, January, February and March.

![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/888edcd8-9e12-4d39-be3b-70890ddefd29)

As part of the data cleaning process which is done in Power Query Editor;

1. I replaced null values with 0 since there was no existing trends to follow for replacement and I was unable to get hold of data owners to give an insight as to why those cells had null values. Under View, enabling Column Quality gives us a glimpse of Empty rows.
![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/df69ebd8-5fe3-444d-bca9-89e8139b0ff6)
![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/c35655a0-7c7f-4c66-85ca-d15324618549)
2. The answered and resolved calls contains Y and N, changing them to Yes and No respectively makes relation easy.
![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/f0efafee-2358-4563-a194-f7f40e18cd25)
3. Two columns “Time” and “AvgTalkDuration” (Changed to Avg. Talk Duration) consisted of both time and date hence need to change to time data type.
   ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/074e4196-644f-4901-a5df-7ac54b0380c2)
   ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/1e65094f-a161-4c11-96aa-b6d2fe88e6ec)

**Creating Measures Using DAX Functions**
1. Number of answered calls
![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/739e6e93-e5bf-4e9c-85a2-4ba353947665)
2. Number of unanswered calls
  ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/4e87ecf8-b072-42ad-a7e9-88eba4244e76)
3. Total Calls = Total answered + Total unanswered calls
   ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/20d36379-00ab-497a-891e-fbd3bf7a4f1a)
4. Resolved calls
   ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/83b72b58-db1c-4454-8f77-78887fcac971)
5. Customer Satisfaction Rating - Calculate your Customer Satisfaction (CSAT) score by dividing the positive responses (satisfied customers) by the total number of responses and multiplying by 100, which is then expressed as a percentage. (Satisfied Customers / Count of Satisfaction Rating) *100
- Satisfied Customers
  ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/ab3efcab-ba4b-470e-8dc6-c63db89a6666)
- Count of Satisfaction Rating
  ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/dec0814d-f18f-4c86-b833-3af8463cb03b)
- Overall Customer Satisfaction
  ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/ba53ea1f-b7e0-42cf-af94-83aaab3aa017)
- Satisfaction rating (Stars)
  ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/e5aa914c-2289-4aa8-b53a-18e963ea946b)
- Separating day from time. After creating this table, make sure to create the relationship in the model view. This will help to determine the busiest days to put more agents on the shifts.
  ![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/361a0188-516d-4dbd-9594-9d595a76db2f)
- I thought of shifts. Most call Centers works in shifts, what could be the shifts that needs more agents. (I couldn't manage this - Researching)

**Creating Dashboard**
I created dashboard in power BI based on the above measures and other parameters.
![image](https://github.com/Essie-Wabomba-dmd/Call-Centre-Trends-Analysis-with-Power-BI/assets/63599016/57026ed5-cbc8-47a0-a9da-7962263d6c23)

**Key Insights**
-A total of 5000 calls were made at the call Centre between 1st January 2021 and 31st March 2021. Out of these calls, 4054 calls were answered which was 85.08% of the calls made and 946 calls were unanswered which was 18.92% of the calls made. Out of the answered calls, 3646 calls were resolved (89.94%) and 408 calls were made and unfortunately they were not resolved (10.06%).
-The customer satisfaction rate is at 40.46% which is below average. This comes with an estimate of 15.75% satisfaction rate of those whose issues were not resolved and 49.64% satisfaction rate of those callers whose issues were resolved.
-At this call Centre, we have 8 agents who I believe have the equal chances of picking the calls. Jim, Dan, Becky and Martha takes the lead in terms of total number of calls, calls received and average talk duration in seconds. Good work! Diane however leads in he number of dropped calls and again he(s) has the most unresolved cases considering he(s) is not among the top 4.
-Call Centre receives about 675 to 770 calls a day with Monday being the busiest and Tuesday being the less busy day. Weekends are busy days as well, Saturday being more busy than Sunday, but Sunday is more busy that Tuesday and Wednesday. This information can be useful when arranging shifts to determine the number of agents to be allocated on a particular shift to minimize the number of unanswered calls.
-Majority of calls are related to streaming and technical support issues. Payment related, administration support and contract related issues are a good number as well. 'other' as an option needs to be added as well to avoid categorizing issues that are not in mentioned list.
-The average speed of answer is 55 seconds.

Note: More insights can be driven from this data as per the dashboard created above. Kindly share your comments on this task and correct where necessary. You can reach me on LinkedIn as well https://linkedin.com/in/esther-wabomba-510a8b123






- 








