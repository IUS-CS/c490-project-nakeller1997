# On Track Budgeting App

## Motivation
My motivation for this app is to basically combine two budgeting apps that I use into one.  I do my best to be responsible with my money and keep track of my spending.  Since I’m a server and make tips I keep track of the money I make on an app called TipSee.  This app shows what I made by day, week, and year in a calendar format to keep it organized.  The heavylifter budgeting app that is used to plan out the monthly budget and keep track of spending daily is called EveryDollar.  The purpose for combining the two apps is that it’s inconvenient to have to manually move my income from TipSee to EveryDollar.  Only needing to input the income one time in one place would be less of a hassle.  This app could be geared towards servers because of the functionality that will come from the TipSee app, but anyone would be able to use it as a general budgeting app.
https://play.google.com/store/apps/details?id=com.wcd.tipsee&hl=en_US
https://www.everydollar.com/?gclid=EAIaIQobChMI_MKN_ICY5QIVSh-tBh0UKgwPEAAYASAAEgJ1yfD_BwE

## Requirements
There are going to be a total of eight screens including landscape view. There will a home, income, income_summary, and item_details screens.

#### Home Screen
The home screen is going to be the where the whole budget is going to be displayed.  At the top of the home screen there is going to be a button labeled 'income' that will take the user to the income screen.  The home screen is going to be a scrollable window that will have set categories that will be savings, housing, transportation, food, and lifestyle.  Each category will have a list of items that the user can add and set the value of.  The home page will show the item name and the value of the item.  If any of the items are clicked on the home page, the item_details screen will be shown.  

![](home_screen.png)   ![](land_home_screen.png)

#### Item Screen
The item_details screen is going to show a running total of the current value of the item and a list of transactions below that.  Each transaction is going to show its name that the user gives, and the total value of the transaction.  The total at the top will show how much was planned to be spent, how much has been spent, and how much is left.  

![](item_screen.png)  ![](land_item_screen.png)

#### Income Screen
The income view is going to have two text boxes, a submit button, and a summary button.  One of the text boxes the user will input their income and the other will take the amount of hours worked.  Below those text boxes is where the submit button will be.  The summary button below the submit button.

![](income_screen.png)  ![](land_income_screen.png)

#### Summary Screen
The summary screen will display the average hourly amount and the total for the week, month and year. Below that will be a list that displays each income that the user has submitted for the month.  

![](summary_screen.png)  ![](land_summary_screen.png)


#### Data Persistence
The data for the app is going to be stored on the device in a SQLite database. Data will be stored each time the user changes a value for an item, enters income, and tracks their spending.  

#### Communication
For outside world communication I was planning on allowing the app to link up to the users bank account.  This is a feature that I would like to have on the apps that I use, but I'm not sure if that should be the goal for this app.  I do not know whether I would be able to secure the app enough to connect to a bank account.  

## MVC Breakdown
### View

#### Home Screen
The home screen is going to display the total income that the user has entered for the month. The user will not be able to edit the number from the home screen.  This number will be retrieved from the summary screen on the creation of the screen. When the income button is clicked the listener will create and display the income screen. The rest of the budget the user will be able to scroll down to view.  The set categories will hold the list of items associated with it and at the bottom of the list will be an add_item button.  The user will be able to edit the name and the total value of each item in the categories from this screen. The add item button will generate a new blank item in the list that the user can edit.  If the user clicks on the middle of an item, the user will be taken to the detailed item screen, and the home screen will be paused.

![](home_screen.png)   ![](land_home_screen.png)

#### Item Screen

The detailed item screen will show each transaction that is made under a specific item. (Ex. in a 'restaurant' item it could hold multiple restaurant transactions.) There will be a plus (+) button at the top of the screen to add the transactions into the list.  When the button is clicked a new blank transaction will be inserted into the list.  Each transaction will have a name and value, and the user will be able to edit the transaction from the list.  The top of the screen is going to show a running total of all transactions.  The three numbers at the top will be planned - spent = remaining.  The user will not edit these numbers because they will be retrieved from the total item value and the total value of the transaction list.  

![](item_screen.png)  ![](land_item_screen.png)

#### Income Screen

The income screen will only be used to input the user's income.  There will be two boxes that the user will type in their income and hours worked.  After the user is finished inputting their data, they will click the submit button.  The data will be stored in the database after.  There will also be a summary button.  When it's clicked the user will be sent to the summary screen and the income screen will be destroyed.  

![](income_screen.png)  ![](land_income_screen.png)

#### Summary Screen

The top of the summary screen will display the total hourly average and the total for the week, month, and year.  The user will only be able to view these values and not edit them.  Below these numbers, there will be a list with each income that has been entered for the month. The incomes in the list will show what the user entered on the income screen.  
