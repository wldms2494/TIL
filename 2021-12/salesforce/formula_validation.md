Formula
======== 
org는 엄청난 양의 데이터를 담고 있다. 유저들은 이 다량의 데이터를 한번에 이해할 수 있어야 한다. 
Formla field를 이용하면, 이 데이터를 어떤식으로 보여줄지 control을 제공한다. 

let's say you wnated to take two numeric fields on a record and divide them to create percentage.
레코드의 숫자필드를 가지고 퍼센테이지로 나눈다고 해보쟈
on perhaps you want to turn a field into clickable hyperlink for easy access to important info from record's page layout
아마도 필드를 하이퍼링크로 체인지하여 레코드 페이지에서 쉽게 접근하고 싶을꺼다
maybe you want to take two dates and caculate the number of days between them.
all these things and more are possible using formula fields
하이퍼링크로 쉽게 접근 하는거나 , 각 날짜의 쉬운계산. 포뮬라 필드와 함께라면 가능하다.

let's look at specific example. what if you wanted to caculate how many days are left until an opportynity's close date?
you can create a simple formula field that automatically calculates that value. 


by adding value to the oppotunity page layout, 영업 페이지 레이아웃에 value를 더해서
your users can quickly access this key info. 
you can also add this field to report and list view for instant 

포뮬러 필드를 만들 옵젝트를 선택한다
예시에서는 opportunity에서 field relationship을 통해 new Formula field를 생성한다

field label 과 함께 formula Return type 포뮬라 반환타입을 선택하는데, 이는 
type of data you expect your formula to return ~
for example, if you want to write a formula that calculates the commission a salesperson receives on a sale, you select Currency. 
판매자가 판매에서 얻은 수수료를 계산하는 포뮬라를 작성한다고 했을때는, 리턴타입이 Currency일거다.

리턴타입 결정 후에는 가장 중요한 furmula editor 가 나온다. 

formula editor comes in two flavors : simple and advanced . it's tempting to use simple editor, but we always recommend using the advanced editor.
advanced doesn't mean more complicated. it means more tools for you to create powerful formulas

insert field button opens a meny that allows you to select fields to use in your formula. 
Inserting from this meny automatically generates the correct syntax for accessing fields.

Insert Operator button opens a dropdown list of the available mathematical and logical operators.
( & concatenate  스트링 서로 붙여주는거)

fuctions meny is where you view and insert formula functions. functions are more complicated operations that are preimplemented by salesforce.
some functions can be used as-is(예를 들어서, TODAY()fuction returns the current date), while others require extra pieces of info, called parameters.
The LEN(text)fuction, for instance, finds the length of the text you input as a prameter
LET은 파라미터로 입력한 텍스트의 글자 길이를 알아낼 수 있어욧
the formula LEN("Hello") returns a value of 5

the text are is where you enter your formula. when writing formulas, keep in mind that :
white space doenst matter. you can insert as many and line breaks as you want witout affecting the formula's execution.
and formulas are case sensitive. pay attention to capitalization(대소문자구분) of field and object names.
when working with numbers, the standard order of operations applies (??)

once you've writtem a formula, you can use the check syntax button to ensure that everything is in working order before saving.
if your formula has issues, the syntax checker alerts you to specific problems.

let's take a single field from account and show it on a contact using what's called a __crros-object formula__
회원에 잇는 필드를 가져가서 연락처 옵젝트에서 보여주겠당

오브젝트와 오브젝트를 가로지르는 포뮬라?

텍스트를 리턴하는 Account Number라는 포뮬라 필드를 만들고 필드 시큐리티까지 설정해쥼
이제 contact의 detail 페이지에서 account number를 확인할 수 있다. 

# Display the number of days until an opportunity closes on a Report

you can also use formula fields in reports to increase the visibility of important info.
say for example, you wanted a report column that displays the number of days until opportunity is closed.
first creat an opportunity to test our formula

to count displaye number of days, we need close date and today's date
but how do wel tell our formula that we need today's date ? luckily there's function calles TODAY() that updates to match the current date
그래서 Report라는 곳에서 add column 을 통해 formula를 추가해 보았다. 

# Find Distinct Objects Using the power of one
Org often want to count the number of uique objets in a report with hundreds of records.
say for instance, you have a hundred opportunities listed in a report, but only a handful of users own all these opportunities.
how do you find the number of distinct users?

this task sounds difficult, but it's one of the easiest formula you can wirte. it's called the power of one
이제 제목이 좀 이해되네
Power of one 을 사용하여 특정 object찾기?ㅎ

to write this formula, create a custom formula field on the user objects 

** parentheses 괄호

## further Example
1. this formula creates a hyperlink to an external website using the HYPERLINK() function. adding hyperlinks to page layouts helps your users access important information quickly from dthe detail pages

2. if you want to apply a discount to an opportunity amount, you can use the following formula. in this case, we're applying a 12% discount and then rounding the result to two decimal places 
using the ROUND() function

ROUND()function을 사용하여 소수점을 rounding 할 수 있음!
`ROUND ( Amount - (Amount * 0.12), 2 )`

3. this formula is a checkbox formula that determines whether a particula opportunity is a "big" opportunity. it checks whether the number of employees at the opportunity account's associated company is greater than 1,000 AND whether the opportunity amount is greater that $!0,000
이 포뮬라는 쳌박스임 특정 영업이 "BIG" 영업인지 결정하는것이지!
OPPORTUNITY의 직원의 수가 1000명 보다 많고, 그리고 영업의 양이 10,000달러 이상인지를 체크하는 것이다. 둘 조건 다 충족한다면, FIELD는 OPPORTUNITY 페이지 레이아웃에서 PZMFH QHDUWLF RJTDLEK. DKSLAUS QLSQKRTMFH QHDUWLSEK. 
AND (Account.NumberofEmployees > 100, Amount > 10000 )

the formulas documentation contains numerous examples for many different use cases.
while you're browsing these examples, keep in mind that many of them contains advanced concepts that wern't cover in this unit.
make sure you're comfortable with the info presented here before takling these formulas

Roll-up Summary Fields
=============

while formula fields calculate values using fields within a single record, 포뮬라 필드가 single record의 field를 사용해서 value를 계산하는 거라면

roll-up summary fields calculate values from set of related records, such as those in a related list.
롤업 서머리는 연관된 레코드들, related list에서 value 를 계산한다.

you can create roll-up summary fields that automatically display a value on master record based on the values of records in a detail record

these detail records must be directly related to the master thorugh a master-detail relationship

like, 
- a custom account field that calculates the total of all related pending opportunities
- a custom order field that sums the unit prices of products that contain a description you specify.

# defining a roll-up summary field
since roll-up summary fields are based on master-detail relationships, it's useful to review object relationships before creating roll-up summary field

### master- detail relationships
master-detail relationships closely link objects together so that the master record controls specific behabiors of the detail and subdetail record.

you define a roll up summary field on the object that is on the master side of a master-detail relationship. for example , you can create a roll-up summary field on the account obejct, summarizing related opportunities:

there are few different types of summaries you can use.
summary 타입! 중요햇
COUNT - totals the number of related reocrds.
SUM - totals the values in the field you select in fhe field to aggregate option. only number, currency, and percent fields are available( date 노노)
MIN - Displays the lowest value of the field you select in the field to aggregate option for all directly related records. only number currency percent date and date/time fields are available.
MAX  - displays the highest value of the field you select in the field to aggregate option for all directly related records. only number currency, percent , date, date/time fields are available.


formula 랑 rollup summay둘다 그냥 계산하는건줄 알았는데
차이점을 이제 좀 알겠다

일단 formual는 한 오브젝트안에서 필드를 보요주는 방식 같고
rollup summary는 두개의 옵젝트 관계속에서 related value를 보여줌

이제 마지막으로 

# validation Rules

validation rules verify that data entered by users in records meets the standards you specify before they can save it.
A validation rule can contain a formula or expression that evaluates the data in one or more fields and returns a value of "True" or "False"
when the validation rule returns a value of "True", this confirms that the data entered by the user contains an invalid value. 
validation rules can also include error messages to display to users when they enter invalid values based on specified criteria.
Using these rules effectively contrivutes to quality data.
for example you can ensure that alll phone number fields contain a specified format or that discounts applied to certain products never exceed a defined percentage.

you can create validation rules for objects, fields, campaign members, or case milestones(중요한단계)/ let's create a validation rule that fires when a user tries to save an account with an account number of inccorect length 


AND(
   NOT(ISBLANK(AccountNumber)),
   NOT(ISNUMBER(AccountNumber))
AND(
   RIGHT( Web_Site__c, 4) <> ".COM",
   RIGHT( Web_Site__c, 4) <> ".com",
   RIGHT( Web_Site__c, 4) <> ".ORG",
   RIGHT( Web_Site__c, 4) <> ".org",
   RIGHT( Web_Site__c, 4) <> ".NET",
   RIGHT( Web_Site__c, 4) <> ".net"
 )


<> 
not equal!

NO.327 Universal Containers needs the 18-digit record ID from Opportunity records when exporting
data to Excel in order to ensure each record is treated uniquely.
What formula should an app builder use to create this new field?
(A). ISNUMBER(Id)
(B). CASESAFEID(Id)
(C). TEXT(Id)
(D). VALUE(Id
