### multi tenant
멀티 테넌시란 소프트웨어의 아키텍처를 가리킴,

하나의 소프트웨어 인스턴스가 한 대의 서버위에서 동작하면서 여러개의 테넌트를 서비스한다. 테넌트란 소트웨어 인스턴스에 대해 공통이 되는 특정 접근 권한을 공유하는 사용자 그룹?

Tenants 를 여러 사용자라고 이해하자

..

단일 소프트웨어 인스턴스로 서로 다른 여러 사용자 그룹에 서비스를 제공할 수 있는 소프트웨어 아키텍처.

SaaS(서비스로서의 소프트웨어)제품이 멀티 테넌트 아키텍처의 예임

Multi-tenancy means that a single instance of the software, database, and supporting infrastructure serves multiple customers, while each tenant’s data is isolated and remains invisible to other tenants.


### Patch Mgmt(patch management 패치관리)

패치관리는 관리자(admin)이 os, platform 또는 애플리케이션 업데이트를 제어하는 것을 뜻함.

process of distributing and applying updates to software

패치란? os, 플랫폼 또는 App의 작동 방식을 결정하는 새로운 코드 또는 업데이트 된 코드입니당

### Embedded ?

embed 끼워넣다, embedded 내장형

기계에 내장되어 있는 소트프웨어

기계를 만드는 것이 아니고 기계들이 작동되게 프로그램을 만드는것.

(전기밥솥, 전자레인지,,등등 기기를 동작할 수 있게 프로그래밍 하는것)

NOC

network Operation center

통신 네트워크가 통제되고, 상태가 체크되며, 유지되는 장소

Backward Compability

compability 호환성, back ward뒤로 → 하위 호환성

새 제품이 이전 제품을염두에 두고 만들어진 제품에서 별도의 수정 없이 그대로 쓰일 수 있는 것을 뜻함.

하위호환성은 제품의 특성이 아닌 두 제품(old and new one) 사이에서 성립하는 관계이며, 호환성의 특수한 경우로 볼 수 있음,  두 제품을 서로 바꿔 쓸 수 있음을 보장하는 호환성이랑은 달리, 하위 호환성은 한 제품이 다른 제품 대신에 쓰일 수 있다는 것만 보장하고 그 반대는 보장하지 않음. 보통 하위 호환성은 이전 제품이 제공하던 인터페이스를 그대로 유지한 채 새로운 기능을 추가하는 식으로 이루어짐



Platform Overview and Certification App
==========================================

이해해야할것

- multi-tenant Architecture
- Layers of a Salesforce Application
- How we connect with Salesforce

### Salesforce
→ CRM Sales Cloud and Service Cloud (which are built on Lightning platform.)


they include application-specific :
**data model
Business logic
User Interface**
Chatter는 social enterprise application included with the sales cloud and service cloud.

그러면 Salesforce가 제공하는 것은 무엇이냐?

- Infrastructure
→ network, storage, Operating System, Database, App server, WebServer, DataCenter(?)
- Application
→ Security, Sharing, integration, Customization, WebSertvice, API, Multi-Language
- Operations
→Authentication, Availability, Monitoring, Patch Mgmt(?), Upgrades, Backup, NOC(?)

Cloud Computing의 속성들은 몬가욧?

- multi tenant
- Subscription(신청?????)
- no large start-up fee 그렇지 왜냐면 서버 종량제가 생각나네
- Fixed, predictable cost
- Scales with your business
- Automatic upgrades

**Salesforce Releases** 

Three product releases per year

Upgrading is automatic and free for all customers

Backward compatibility (하위 호환성) for the API and any programmatic

 customizations you make

Development environments are upgraded early for testing.

Layers of a Salesforce Application

Salesforce customization(사용자 정의) will be against one or more of these three layers

User Interface + Business Login and Automation + Data


## Declarative vs Programmatic Customization

declarative dev on Salesforce 세일즈 포스에서의 선언적 개발?

→ Applications built on the Salesforce platform automatically have : 

- Secure Access
- Integrated business logic
- Report and analysis
- Data management

with just clicks!~

그럼  왜 Salesforce?

→Simplicity + Speed

make the most of declarative capabilities

- faster than coding
- Easier to maintain
- Automatic access to updates of the feature set
- No coding skills required

→ Custom Functionality + Integration(통합, 시스템 전체의 업무를 주도적으로 관리하는 일.)

User programmatic customizations for : 

- greater flexibility and more complex logic. 그럼그럼...
- more control over user interface
- More integration options.
