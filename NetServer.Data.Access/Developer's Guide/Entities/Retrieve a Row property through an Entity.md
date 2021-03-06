<properties date="2016-05-11"
SortOrder="63"
/>

A property which is of Row type directly refers to a particular row of a table. For example in the Sale Entity the Currency property would refer to the Currency table and would contain the columns that are in the Currency Table as its properties.

```
using SuperOffice.CRM.Entities;
using SuperOffice.CRM.Rows;
using SuperOffice;
 
using(SoSession mySession = SoSession.Authenticate("SAL0", ""))
{
      //Retrieving an Entity
      Sale newSale = Sale.GetFromIdxSaleId(2);
 
      //Retrieving Properties of a Row through an Entity    
      string saleCurname = newSale.Currency.Name;
      if (newSale.Currency.Deleted == 0)
      {
            string saleCurAct = "Sale Currency Active";
      }
      else
      {
            string saleCurInAct = "Sale Currency Not Active";
      }
      string saleCurDB =     
newSale.Currency.CurrencyTableInfo.DbName;
      string saleCurRate = newSale.Currency.Rate.ToString();
      string saleCurRank = newSale.Currency.Rank.ToString();
      string saleCurRegDate =      
newSale.Currency.Registered.ToString();
      string saleCurUnits = newSale.Currency.Units.ToString();
}

 
```

Here we have retrieved the properties of the currency Row of the currency table through a Sale Entity.

 
