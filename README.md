# Salesforce SOQL & SOSL

Here you will find best practices and tips & tricks of Salesforce SOQL and SOSL query languages.

```
(A) SOQL = Salesforce Object Query Language
(B) SOSL = Salesforce Object Search Language
```

### (A) SOQL

(1) String literals in Dynamic query 

```
String stage = 'Closed Won';
String query = 'SELECT Id, Type, (SELECT Id FROM Opportunity WHERE StageName = \'' + stage + '\'';
query += ' AND CreatedDate = LAST_N_DAYS:30) FROM Account WHERE IsPersonAccount = true AND AnnualRevenue > 1000';            
```

<b>Note:</b> You can't use "ApplicationConstant.STAGE_NAME_CLOSE_WON" with replacement of stage variable.
