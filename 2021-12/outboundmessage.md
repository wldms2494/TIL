outboudmessage?
=======

proactive service?proactive 관행... 흠
proactive service means that instead of waiting for customers to reach out with problems, you can preempt(선점한다) complaints by reaching out to customers first.
proactive service란 고객이 문제에 도달하는것을 기다리는것 대신에, 먼저 고객에게 다가가 고객의 컴플레인을 선점하는 것이다. 

this narrows down the options to outbound messaging, expecially since she read on the salesforce blog that it has the potential to save 50% over the cost of using voice call

sooooo
outbound Messaging ! lets you customers stay engaged and informed in ways that are most convenient for them - on their mobile devies using a phone number or messaging apps, such as sms text messaging, 
facebook messenger, and whats APp

outbound messaging 에는 2Types 가 있다. 
- outbound
- triggerd


#### outbound 부터 먼저 보쟝 . 
나는 아웃바운드 메세지는 하나의 방식으로 trigger방식(약간 자동화)이런 느낌으로는 예상하고는 있었지만 2가지의 타입이 나눠질줄은 몰랐다 
Description : 
agent initiates a conversation with a customer. outbound messages are ideal for proactively engaging with a customer either resolve an issue, follow up to a previous question, or as a check in to strengthen the overall relationship.
 example : 
 agent follow up to an existing case or customer question 
 상담사는 존재하는 case나 고객의 질문에 더 알아본다. 
 account rep connection with their customer
 고객과 판매자의 연결
 sales order follow up
 follow up은 더 알아본다는 뉘앙스인듯
 shipping error resolution
 appointmnet rescheduling
 
 
#### tiiggered 도 알아보쟝
 process or workflow that automatically sends a message to customers preferred mobile messaging app based on changes to their customer record
 process 또는 workfolow이며 고객의 레코드가 변화되는것을 기반으로 자동으로 고객이 원하는 메세지앱에 message를 자동으로 보내는 것이다. 

shipping update
purchase confirmation
payment received
appointment confirmation or reminder
security alerts like identity verifications or password resets
id확인과 비밀번호 동기화 등 보안과 관련된거 경고함
order status or where is my order(WISMO);;;updates
bill payment reminders 돈내는거 리마인드시킴
surveys or feedback


it's important to differentiate messaging from a chat session. 쳇 세션에따라 구분짓는것도 중요하다 
messaing happens over third party channel like what's app, facebook messanger whereas chat is window that pops up on a desktop or mobile web browser for customer service conversation
message는 비동기화 (asynchronous )이며, 이는 대화가 동시에 일어나지 않음을 의미한다. 동기화라는 정보의 최신성을 동일하게 한다?
chat 은 synchronousdlai 이며 이는 대화가 동시에 일어남을 의미한다. 


뭐 보니 이런것 같당
 outboundmessaging 은 서비스 품질 향상을 위해 고객들이게 연락을 취하는것임 뭐 메세지를 보내는거, 전화거는거, 챗하는것이 될 수 있고
 자동화는 trigger이고 직접agent에 의해지는것은 outbound messaging이라고 하는것 같다.
 
 consumers need to provide explicit consent to engage in a conversation on short codes.
 shortcodes는 5,6digits전화번호로 문자보내는거고 손님이랑 대화도 가능한것인디 
 일단 이거를 하려면 법률상 명백한 동의가 필요로 한다.
 
 benefits?
 많겠찌 예상 가능하지......
 
 prerequisite 이런 단어 첨본당
 prerequisite 전제조건!!!
 ## prerequisites for ountbound messaging
 there are many ways to set up outbound messaging.
 and there are the prereqiosotes upi meed tp cpmsoder before you begin.!
마치 키친 싱크사는거랑 비슷하다고 한다.. 싱크 사는 전제 조건으로 음 파이프나 워터나 기초적인것이 갖춰진건지.. 몬가 끼워맞춘듯한 예시 맘에 안듬ㅋ
 
 
 
 <img src= "https://user-images.githubusercontent.com/80088918/151103863-3fe2b34d-d9c8-4d12-9701-9e75a556f756.png">
 
 
 2번 틀림
 Omni-Channel: Messages are automatically routed to agents who are logged in to the Omni-Channel utility in the console.
 Customer responses go directly to the agent who initiates an outbound message when logged in or to an available agent logged in to Omni-Channel. 
 Outbound messages do not count toward your Omni-Channel capacity.
 
# prepare for outbound messaging
아웃바운드 메세지 준비하기

adding multiple channels is the second stage of the general setup process for service cloud
여러개의 채널을 더하는것은 서비스클라우드의 일반적인 셋업에서 두번째 단계이다
having set up case management(case 관리 셋업)은 첫번째 단계이다.!
if the right case field, notifications, and routing processes are not implemented, 
it doesnt matter if agents message customers because they'll be too busy to trying to figure out how to capture the right info and determine who should work each case
그래서 case management가 우선적으로 행해져야 한다는 말인듯.

before maria se up outbound messaging, she presents the service team with messaging options.

do we want to automates some of our messages?
-> yes, let's automate outbound whatsApp messages with templates to let our customers know when our agents are working on theirs cases. we can automate those messaging templates with the __Process Builder__
Do we need to create bots to automate interactions or update records?
-> yes, we could definitely use our exisiting Einstein Bots implementation to automatically thank customers who respond to our outbound whatsapp messages and to display a list of meny options based on the solar panels that they purchased.

<img src = ""https://user-images.githubusercontent.com/80088918/151106123-e5a0b90f-1191-41e9-b5ff-e877673de700.png>
# turn on outbound messaging
# Rollout Outbound Messaging 
Start with a small test of trial customers. Begin with a specific location or allow only some customers to message you, such as VIP or Platinum Support customers. See what works best for those customers before beginning a larger rollout.
Create a library of templates or automated messages for agents. Build a wiki of text-friendly phrases and emoticons that match your brand and streamline frequent responses to customers.
Train your agents. Teach agents how to initiate conversations with customers from the Service Console and how to use templates or automated messages to deliver consistent customer experiences.
<img src = "https://user-images.githubusercontent.com/80088918/151109308-570d5df8-964f-44de-94a2-6616a08ddf08.png">
