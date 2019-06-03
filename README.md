# Tip Calculator Project

### **Please [click here](https://tip-calculation-project.herokuapp.com/invoice.html) to visit the app page.**

Tip calculator with interactive interface for coding challenge. Simple program that takes in inputs of price and tip percentage and returns the price, the tip amount based on the tip percentage, and the total bill. The program also allows the user to split the bill and will calculate those values in terms of order price, tip amount, and total amount.

## **How It Works**

When the users first access the site, the time at which they accessed the site will be recorded as the day the invoice was issued, and the due date of the payment will be two weeks from that time. These values will be populated automatically.

Users will are given a few fields to fill out, and a number of consequences will occur when certain buttons are pressed. The possible input areas are:
1. Price and Tip values.
2. The number of individuals to split the bill by
3. Payment through cash, credit, or check.

If credit is selected, additional menus prompting the user to input their credit card and CVV number will be given. A validate button with the user's card information will then appear to allow for the user to check if their card works 

It just checks to make sure that the format is valid - make sure the dropdown menu matches your card provider (i.e. Visa, MasterCard)if you want to try it out! 

Below is an example:

![Preview](https://i.imgur.com/fGpxUpv.png)

#

Users are expected first to enter in the price of their meal and the tip (in %), then press submit information. 

This will lead the script to automatically process the calculation. The order value, tip value, and total value will update in the bottom right hand corner in their respective rows if a valid value is entered; the calculation is truncated to two decimal places, as specified in the initial requirements of the project.

A series of if - else if - else statements in the logic.js file handles a set of possible errors or nonsensical inputs:

**Either Price or Tip Input Value is Missing**
* The user will receive a red prompt at the bottom of the submit information button prompting them to fill out both values. No calculation will be processed, of course. 
* This failure condition will take precedence over other failure conditions. For example, if one value is missing and the other is negative, then the prompt to appear will concern only the missing value.

![Preview](https://i.imgur.com/afbnqoX.png)

**Negative Numbers**
* If one or more of the the user's inputs is negative, the program will prompt the user to make their number positive, but it will still perform the calculation by taking the absolute value of that number. A red prompt will be triggered and then disappear after about two seconds to notify the user of the issue with their input.

![Preview](https://i.imgur.com/zoqkBQQ.png)

**User Inputs a Zero Price**

* If the user inputs a zero price, they will be prompted to rectify the fact that they want to perform a tip calculation on a free meal.

![Preview](https://i.imgur.com/xX30mG2.png)

**User Does Not Tip**
* The user will be informed that it is rude not to tip, and that no calculation will be performed because it does not make sense to calculate a tip when no tip is given.

![Preview](https://i.imgur.com/7w5NTGx.png)

**User Mixes Letters and Numbers**

* If the user adds in letters or other unexpected symbols such as "-" or "*", they will receive a prompt informing them that they need to remove those symbols and that they cannot mix letters or special characters with numbers.

![Preview](https://i.imgur.com/ax4K3Al.png)

After the user enters in a valid number - as defined by a value that doesn't fall into any of the above categories - they will have an option to split. Note that if the user attempts to enter in a value into the split input before a calculation for a tip is made, they will receive a message prompting them that they must first enter in a price and tip, then receive a calculation before they can split. The split input also will catch errors such as negative numbers, missing input, and inappropriate characters.


## **Dependencies and Templates**

### 1. Graphical Interface.

The graphical interface is borrowed from Wes Cossick's HTML invoice template available [at this Github repository](https://github.com/sparksuite/simple-html-invoice-template). I chose Cossick's invoice template because it was minimalistic and clean, and perfect for summarizing the components of this project in a concise, visually pleasing way.

Below is a preview of the template format.

#### Preview
![Preview](http://i.imgur.com/C3ePdqQ.png)

### 2. Odometer.js

The second tool that I used to achieve some of the visual impact I wanted for the price displays was [odometer.js by Zack Bloom](https://github.hubspot.com/odometer/docs/welcome/). I wanted a loading effect after the user pressed the submit information button that would make it obvious to them that their calculation had just been processed. Like its name, odometer.js allows users to pass a number to a odometer classed element in the HTML DOM, and it will then animate that number.

#### Preview
![Preview](https://i.imgur.com/YypVumS.png)

### 3. Credit Card Validation Script.

Adapted from [this site](https://www.braemoor.co.uk/software/_private/creditcard.js). The method checks for the validity of a credit card based on the credit card provider and the expected format of that provider's issued credit card number. I included this to give a sense of authenticity and as an extra fun feature to be associated with the dropdown menu options of "Credit", "Cash", and "Check."

Here is the description of the scripts functionalities from the raw js file:

This routine checks the credit card number. The following checks are made:

1. A number has been provided
2. The number is a right length for the card
3. The number has an appropriate prefix for the card
4. The number has a valid modulus 10 number check digit if required

### 4. Remaining Dependencies

Bootstrap for CSS and JQuery for Javascript were included as additional libraries in this project.