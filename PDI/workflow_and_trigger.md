NO.135 The following automations already exist on the Account object;
* A workflow rule that updates a field when a certain criteria is met
* A custom validation on a field
* A How that updates related contact records
A developer created a trigger on the Account object.
What should the developer consider while testing the trigger code?
(A). The flow may be launched multiple times.
(B). Workflow rules will fire only after the trigger has committed all DML operations to the database.
(C). A workflow rule field update will cause the custom validation to run again.
(D). The trigger may fire multiple times during a transaction.


for a first, 

i searched the reason why flow launch multiple times in trasaction.
it can be caused by the existence of duplicate Record Triggers for the same Flow. 
or
the issue can be caused by the flow;s condition being met twice on the same GlideRecordupdate
glide? android loading library?  i can't get it!!!!!!!

in this question, there's no metion about posiblity to be exist duplicate Record trigger.. i think . so no!

for b , 
workflow rules will fire only after trigger has comitted all DML operations to the database

let's remind the execution order in transaction.

1) Fetch the data
2) System validation
3) Execute before triggers
4) System and custom validations
5) Save the data
6) After triggers
7) Assignment rules
8) Auto-response rules
9) workflow rules
10) workflow field update - if record is updated then before update triggers and after update triggers are called
11) escalation rules
12) entitlement rules
13) Rollup summary field
14) criteria based sharing rules
15) commit
16) send email

after tigger excuted, workflow rules start and the workflow field update. 
after few steps more, they finally commite the data in database
so that's wrong answer

for c , 
workflow rule field update will cause the custom validation to run again ?
what?
in this question there's custom validation rule, which starts after before trigger excuted.
before field updated, they should check is validate data. not after field update. so they don't run validation rule again . so wrong!

for d,
trigger may fire multiple times during a transaction 
i'm not 100%sure about this answer point, but during trasaction be fore save data , before trigger works, and after save the data, after trigger works
this we can say multiple times? ..hmm but i think this is the right answer anyway

 i hope someone could tell me about right solution about this question ! or discuss together 
