## prevent SOQL Injection in SF dev
Injection flaws occur when untrusted data is sent straight to the interpreter as part of a query or command. 
In this case, the attcker is deliberately (intended) passing hostile data (stacked) with the intent of tricking the interpreter into executin uninteded commands or 
gaining commands or gaining access to unauthorized data

so point is, with sf Dev, we need to pay very special attention to SOQL injection.
Orgs are putting thier mopst trusted info into SF with the understanding that the data is secure.
As a developer of Salesforce applications, !!!
part of your job is to uphold the security put in place by the __Force.com platform.__
A big part of this making sure that the custom code you write cannot be used to cause any hard to the organizations using your code.

Salesforce.com has provided us developers some greate materials to read about SQOL Injection. 

`String sQuery = "SELECT* FROM customers WHERE accountID = "" + request.getParameter("id")+"";`

in here, the attcker can modify the "id" parameter in ther browser address bar or throght an program they wrote to send: ' or '1'=1 (???)
this would change the meaning or the query -> resuling in all of the records from the custromer database to be returned instead of only the ineteded csutomers.

dynamic SOQL is the creation of SOQL statements on he fly during the execution of Apex code.
An example of dynamic SOQL would be building a custome search based on input from a form that the user has fileled out.
Dynamic SOQL is very powerful and conveninent but from a security standpoint it is something to approach with caution and care.

To create a dynamic SOQL query at runtime you will use the db query method provided. Below are tow examples of building dynamic SOQL at runtime 

Return a single sObject when query comes back with one record:

sObject S = Database.query(string_limit_1);

Return a list of sObjects when query comes back with more than one record:

List<sObject> L = Database.query(string);

What you want to make sure of is that when you construct the actual query you use the escapeSingleQuotes method. This method is a major time saver and adds the escape character \ to al single quote marks in strings that are passed in from the user. This basically takes an single quote marks and treats them as enclosing strings rather than database commands. It's pretty slick and very important!

Take a look at this example of SOQL Injection Vulnerability in Apex (taken from here)

In this example, lets assume that there is a single input field where the user enters a name. The name is then used to find all Contacts with that name that have not been deleted.

String qryString  = 'SELECT Id FROM Contact WHERE (IsDeleted = false and Name like \'%' + name + '%')';

Now, under normal operation the user would enter something like "salesforcegeneral" and the resulting string would be:

qryString  = SELECT Id FROM Contact WHERE (IsDeleted = false andName like '%salesforcegeneral%')

The problem comes when a malicious user types in something like test%') or (Name like '

 In this case, we'd end up with something like this:

qryString  = SELECT Id FROM Contact WHERE (IsDeleted = false and Name like '%test%') or (Name like '%')

 The result of this query is not just deleted contacts but ALL contacts. The Salesforce documentation gives you a great method to combat this - avoid dynamic SOQL and user static queries with variables. Here is an example of how the above vulnerability is re-written:

String queryName = '%' + name + '%';

queryResult = [SELECT Id FROM Contact WHERE (IsDeleted = false and Name like :queryName)];

I've switched over to this method. If there is no way around dynamic SOQL, which there usually is, make sure to use the escapeSingleQuotes method talked about a few paragraphs up.
  
  
  
  
  
