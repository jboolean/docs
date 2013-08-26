---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---

Throttle your customer subuser when you need them to send only a specific amount of emails at a specified interval.


{% anchor h2 %} Retrieve {% endanchor %}


Retrieve account limits for a specific customer subuser. If the API call response is empty that means the customer subuser has the limits removed.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|
|task|Yes|Must be set to *retrieve*|Retrieve account limits|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who will have their account limits retrieved|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=retrieve {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<credits>
   <credit>0</credit>
   <credit_remain>2000</credit_remain>
   <last_reset>2011-02-21</last_reset>
</credits>

{% endcodeblock %}


### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=retrieve {% endcodeblock %}

### Response: Success

{% codeblock lang: javascript %} {"credit":"0","credit_remain":"2000","last_reset":"2011-02-21"} {% endcodeblock %}

### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} No Limit {% endanchor %}


Obtain a complete list of all customer subuser.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|
|task|Yes|Must be set to *none*|Remove account limits|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who will have their account limits removed|

{% xmljsontabs subuser %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="subuser-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=non {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="subuser-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=non {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Recurring Reset {% endanchor %}


A recurring reset will allow you to periodically reset a subusers credits to a number you specify. This can be either daily, weekly or monthly.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|
|task|Yes|Must be set to *recurring*|The task required to set the recurring reset|
|user|Yes|Customer subuser must be registered under your account|The customer subuser you will be applying a recurring reset to|
|credits|Yes|Must be an integer and greater than 0|The number of credits the customer subuser will be reset to|
|period|Yes|Must be either daily, weekly, or monthly|How often you want SendGrid to reset your customer subusers credits|
|startdate|No|Date must be in YYYY-mm-dd format|The date you want to start resetting the customer subusers credits|
|enddate|No|Date must be in YYYY-mm-dd format|The date you want to stop resetting the customer subusers credits|
|initial_credits|No|Must be an integer greater than 0|The number of credits you initially want the account reset to. If this is not set, the credits will be reset using the credits parameter|

{% xmljsontabs reset %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="reset-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=recurring&credits=200&period=daily {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="reset-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=recurring&credits=200&period=daily {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Total Credits {% endanchor %}


Set a subusers credits to a specified amount.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|
|task|Yes|Must be set to *total*|Set the credits to the specified amount|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who will have their credits updated|
|credits|Yes|Must be an integer and greater than 0|The total number of credits the customer subuser will be reset to|

{% xmljsontabs total %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="total-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=total&credits=20 {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="total-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=total&credits=20 {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Increment Credits {% endanchor %}


Increment a subusers credits by a specified amount.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|
|task|Yes|Must be set to *increment*|Increment the credits by the specified amount|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who will have their credits incremented|
|credits|Yes|Must be an integer and greater than 0|The total number of credits the customer subuser will be incremented by|

{% xmljsontabs increment %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="increment-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=increment&credits=20 {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="increment-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=increment&credits=20 {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Decrement Credits {% endanchor %}


Decrement a subusers credits by a specified amount.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---
-|
|task|Yes|Must be set to *increment*|Decrement the credits by the specified amount|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who will have their credits decremented|
|credits|Yes|Must be an integer and greater than 0|The total number of credits the customer subuser will be decremented by|

{% xmljsontabs decrement %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="decrement-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=decrement&credits=20 {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="decrement-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=decrement&credits=20 {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


</div>
</div>
