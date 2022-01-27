business has questions, and salesforce data has answer 이말 왤케 머싯냐
when you get asked to build a report, request comes in the form of question.
like
- which products are my top sellers?
- who are my highest values pospects?
- which marketing campaigns have been the most successful?
- how satisfied are my customers? 

Question을 까보자
original question : which products are my top sellers?
그러면 
follow-up questions은 
what makes a product a top seller, revenue or quantity?
do you want to see the results grouped by  product family?
what is your date range?
if we stop seling a product, should it show on the report?

그러면 requirements는 
팔로업에대한 요구죠!@
what makes a product a top seller, revenue or quantity?
-> top sellers here meanse quantity rather than revenue.
do you want to see the results grouped by  product family?
-> group products by product family
what is your date range?
-> show all closed won opportunities( 성공 영업을 보여조랑?)
if we stop seling a product, should it show on the report?
-> do not show inactive products

### criteria
이제 이 요구사항에 맞춘 criteria를 작성하는 것이
Report Type = Opportunities with Products  
Report Format = Summary  
Grouping = Product Family  
Show = All Opportunities  
Date Field = Close Date (close를 원하니까 필드는 이게 필요하것지) 
Range = Current FY  (현재 회계년도)
Filter = Product ‘equals’ Active  
Filter = Opportunity Stage ‘equals’ Closed Won  
Filter Logic = 1 AND 2  


# Report
is list of records that meet the criteria you define in Salesforce in rows and columns, and can be filtered, grouped, displayed in praphical chart.

Every report is stored in a forder. folders can be public , hidden, or shared, and can be set to read- only or read/write
control who has access to the contents of the folder based on roles, permissions public groups, and license type(??). 
you can make a folder available to your entire org, or make it private so that only the owner has acess(이거는 owd에 대한 이야기인건강?)

# dashboard
dashboard is visual display of key metrics and trends for records in ur org.
the relationship between a dashboard component and report is 1:1; for each dashboard component, there is a single underlying report.
however you can use the same report in multiple dashboard componets a single dashboard( like use the same report in both a bar chart and pie chart)


# report type은 모임?
레코드 타입 노노
report type is like a template which makes reporting easier.
레포트를 쉽게 작성하기 위한 레포트타입이다. 
the report tupe deter,omes whiches fields and records are available for use when creating report
this is based on relationships between a primary object 랑 related objects
예를 들어서
contacts and accounts 레포트 타입은, Contact is primary objects and accounts is the related object
뭔소리야.. 
reports display only records that meet the criteria defined in the report type. out of the box(즉시 설치 가능한, 기존의 틀을 깨는 사고방식)박스에서 바로 깐고,
out of the box , salesforce provides a set of predefined satadard report types

<img src = "https://user-images.githubusercontent.com/80088918/151279566-b2642d2a-29a3-4d2c-b3a5-18e5e0edd68e.png">
2번의 답은 A였음
