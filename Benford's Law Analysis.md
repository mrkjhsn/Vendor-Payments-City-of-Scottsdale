## Benford's Law Applied to Scottsdale Vendor Payments 
___
#### [Benford's Law](https://en.wikipedia.org/wiki/Benford's_law) states that in many naturally occurring collections of numbers, the leading significant digit is likely to be small. For example, in sets that obey the law, the number 1 appears as the leading significant digit about 30% of the time, while 9 appears as the leading significant digit less than 5% of the time. If the digits were distributed uniformly, they would each occur about 11.1% of the time.  The law has applications in determining if a set of transactions are fraudulent since a person forging transactions would likely ensure the numbers forged are random.


### Am I able to identify oulier vendors in the Scottsdale vendor payments dataset?  Below is the process I worked through to answer this question:
  + ### strip the leading digit off the *PaymentAmount* column
  + ### for each vendor, find the count of leading digits from 1 - 9  
  + ### for each vendor, find the percent each digit from 1 - 9 makes up of total digits
  + ### filter for vendors with at least 50 payments(I reasoned that 50 payments would be adequate to allow for a distribution approximation against the benchmarks outlined by Benford's Law.)
  + ### filter for exception vendors that meet either of the below criteria:
    + ### vendors with a 1 leading digit count that makes up less than 20% of total digits for that vendor
    + ### vendors with a 9 leading digit count that makes up greater than 10% of total digits for that vendor
___  

### Graph of all City of Scottsdale vendor payments leading digits against guidlines outlined by Benford's Law.

![](https://github.com/mrkjhsn/Vendor-Payments-City-of-Scottsdale/blob/master/visualizations/Benford's%20Law%20Graphed%20Against%20Scottsdale%20Vendor%20Payments.png)
<br/>
<br/>
<br/>
### Graph of vendors who have received at least 50 payments from the city.  
![](https://github.com/mrkjhsn/Vendor-Payments-City-of-Scottsdale/blob/master/visualizations/Leading%20Digit%20Frequencies%20for%20Vendors%20With%20At%20Least%2050%20Payments.png)
<br/>
<br/>
<br/>
### 17 vendors had a 1 leading digit count that makes up less than 20% of total digits for that vendor or a 9 leading digit count that makes up greater than 10% of total digits for that vendor.
![](https://github.com/mrkjhsn/Vendor-Payments-City-of-Scottsdale/blob/master/visualizations/Anomaly%20vendors%20-%20list.png)
![](https://github.com/mrkjhsn/Vendor-Payments-City-of-Scottsdale/blob/master/visualizations/Anomaly%20Vendors%20Based%20on%20Benford's%20Law.png)

## **Results:** 

### Some of these vendors, such as Safelite Autoglass, appear to provide services that would likely be about the same amount.  For instance, Safelite Autoglass probably has a flat fee to change windshields for City of Scottsdale vehicles.

### As an auditor, I would want to make a higher number of selections from some of these.  Especially those with less familiar Business names such as  HSS Inc., Univar USA Inc., or Thermo Fluids Inc.
