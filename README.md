# Association-Rule:
Association rule mining is a technique to identify underlying relations between different items.Take an example of a Super Market where customers can buy variety of items. Usually, there is a pattern in what the customers buy. For instance, mothers with babies buy baby products such as milk and diapers. Damsels may buy makeup items whereas bachelors may buy beers and chips etc. In short, transactions involve a pattern. More profit can be generated if the relationship between the items purchased in different transactions can be identified.

# Apriori Algorithm for Association Rule Mining:
There are three major components of Apriori algorithm:

(I) Support

(II) Confidence

(III) Lift

We will explain these three concepts with the help of an example.

Suppose we have a record of 1 thousand customer transactions, and we want to find the Support, Confidence, and Lift for two items e.g. burgers and ketchup. Out of one thousand transactions, 100 contain ketchup while 150 contain a burger. Out of 150 transactions where a burger is purchased, 50 transactions contain ketchup as well. Using this data, we want to find the support, confidence, and lift.

(I) Support:
Support refers to the default popularity of an item and can be calculated by finding number of transactions containing a particular item divided by total number of transactions. Suppose we want to find support for item B. This can be calculated as:
 
  Support(B) = (Transactions containing (B))/(Total Transactions)

e.g.  For instance if out of 1000 transactions, 100 transactions contain Ketchup then the support for item Ketchup can be calculated as:
      
      Support(Ketchup) = (Transactions containingKetchup)/(Total Transactions)

      Support(Ketchup) = 100/1000
                       = 10%

(II) Confidence:
Confidence refers to the likelihood that an item B is also bought if item A is bought. It can be calculated by finding the number of transactions where A and B are bought together, divided by total number of transactions where A is bought. Mathematically, it can be represented as:

  Confidence(A→B) = (Transactions containing both (A and B))/(Transactions containing A)

e.g. Coming back to our problem, we had 50 transactions where Burger and Ketchup were bought together. While in 150 transactions, burgers are bought. Then we can find likelihood of buying ketchup when a burger is bought can be represented as confidence of Burger -> Ketchup and can be mathematically written as:

    Confidence(Burger→Ketchup) = (Transactions containing both (Burger and Ketchup))/(Transactions containing A)

    Confidence(Burger→Ketchup) = 50/150
                               = 33.3%
  
  (III) Lift:
  Lift(A -> B) refers to the increase in the ratio of sale of B when A is sold. Lift(A –> B) can be calculated by dividing Confidence   (A -> B) divided by Support(B). Mathematically it can be represented as:
  
   Lift(A→B) = (Confidence (A→B))/(Support (B))  
   
 e.g. Coming back to our Burger and Ketchup problem, the Lift(Burger -> Ketchup) can be calculated as:
 
     Lift(Burger→Ketchup) = (Confidence (Burger→Ketchup))/(Support (Ketchup))

     Lift(Burger→Ketchup) = 33.3/10
                          = 3.33
  
  
  # Steps Involved in Apriori Algorithm
  
  For large sets of data, there can be hundreds of items in hundreds of thousands transactions. The Apriori algorithm tries to extract rules for each possible combination of items. For instance, Lift can be calculated for item 1 and item 2, item 1 and item 3, item 1 and item 4 and then item 2 and item 3, item 2 and item 4 and then combinations of items e.g. item 1, item 2 and item 3; similarly item 1, item2, and item 4, and so on.

As you can see from the above example, this process can be extremely slow due to the number of combinations. To speed up the process, we need to perform the following steps:

1. Set a minimum value for support and confidence. This means that we are only interested in finding rules for the items that have certain default existence    (e.g. support) and have a minimum value for co-occurrence with other items (e.g. confidence).
2. Extract all the subsets having higher value of support than minimum threshold.
3. Select all the rules from the subsets with confidence value higher than minimum threshold.
4. Order the rules by descending order of Lift.
  
  
