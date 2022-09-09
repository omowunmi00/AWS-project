### **Using AWS Budgets to set custom budgets for tracking costs and usage of resources, set up alerts by email when actual or forecasted cost and usage exceed budgeted threshold on AWS account**

From management console search and click to open `AWS budget`

click on `create budget`. There are 4 major steps to follow;

> Step 1: Choose your `budget type` and click next.

![Image not found](budgettype.png)

> Step 2: `Set your budget`. Here, there are 3 fields to fill; 
    
    i. Enter your budget details, fill in the "Budget name" field

![Image not found](budget1.png)

    ii. Set budget amount, also select recurring if you want the budget to renew on the first day of every monthly biling period 

![Image not found](budget2.png)

    iii. scope of budget (Ensure ALL AWS services is selected: this will track any cost incurred from any service from your account). 

![Image not found](budget3.png)

`NOTE`: click advance option and select refunds and credits in addition to the selected charge types.

> Step 3 & 4: `Configure alerts and attach actions`. Select alert threshold and specify receipient and how you want them to receive the alert. For learning purposes, I will recommend you set email receipients only as SNS may incur extra charges.   
For threashold measured againt: Select actual or forecasted cost 

`NOTE`: You can specify up to 10 email receipients.

![Image not found](createactions.png)

Review to confirm your selected choices then create your budget.

![Image not found](Review.png)

![Image not found](Success.png)



# **THANK YOU FOR READING** 


